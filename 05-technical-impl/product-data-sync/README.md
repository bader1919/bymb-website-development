# Product Data Mapping System - Hikvision to BY MB

**Version:** 1.0  
**Date:** June 21, 2025  
**Purpose:** Automatic synchronization of manufacturer product data to BY MB website

---

## ? System Overview

This system automatically pulls product data from Hikvision's official website and maps it to your BY MB Consultancy product structure, ensuring your website always has the most current specifications, features, and technical details.

### Key Features
- **Automatic Data Sync** - Regular updates from manufacturer sources
- **Intelligent Mapping** - Converts manufacturer specs to BY MB format
- **Price Calculation** - Applies your markup and VAT automatically
- **Odoo Integration** - Direct updates to your website database
- **Error Handling** - Robust fallback mechanisms
- **Audit Trail** - Complete logging of all changes

---

## ? Technical Implementation

### Data Sources Supported
1. **Hikvision Official API** - Primary data source
2. **CSV Backup Files** - Fallback when API unavailable
3. **Manual JSON Files** - Custom product additions
4. **Web Scraping** - Alternative extraction method

### Mapping Process
```
Hikvision Data ? Data Mapper ? BY MB Format ? Odoo Database ? Website Display
```

### Price Calculation
- **Wholesale Price** (from supplier)
- **+ 10% VAT** (Bahrain standard)
- **+ 35% Markup** (from Knowledge Center)
- **= Final Retail Price**

---

## ? File Structure

```
05-technical-impl/product-data-sync/
??? sync_system.py                 # Main synchronization system
??? hikvision_mapper.py            # Hikvision-specific mapping
??? odoo_integration.py            # Odoo database integration
??? config/
?   ??? sync_config.json          # Configuration settings
?   ??? field_mappings.json       # Data field mappings
??? data/
?   ??? hikvision_products.csv    # Backup product data
?   ??? manual_products.json      # Manual additions
??? logs/
?   ??? sync_logs.txt             # System logs
??? README.md                     # This documentation
```

---

## ?? Configuration

### sync_config.json
```json
{
    "odoo": {
        "odoo_url": "https://www.by-mb.com",
        "database": "by_mb_database",
        "username": "admin",
        "password": "your_secure_password"
    },
    "sync_settings": {
        "auto_update_hours": 24,
        "backup_before_sync": true,
        "notify_on_errors": true,
        "markup_percentage": 35,
        "vat_rate": 10
    },
    "data_sources": {
        "hikvision_api": "https://api.hikvision.com/products",
        "backup_csv": "data/hikvision_products.csv",
        "manual_json": "data/manual_products.json"
    }
}
```

---

## ? Usage Instructions

### 1. Initial Setup
```bash
# Install dependencies
pip install requests python-dateutil openpyxl

# Configure settings
cp config/sync_config.example.json config/sync_config.json
# Edit with your Odoo credentials
```

### 2. Manual Sync
```bash
python sync_system.py
```

### 3. Automated Sync (Daily)
```bash
# Add to cron for daily updates
0 2 * * * /usr/bin/python3 /path/to/sync_system.py
```

### 4. Monitor Results
```bash
# Check sync logs
tail -f logs/sync_logs.txt
```

---

## ? Data Mapping Examples

### Hikvision ? BY MB Mapping

#### Model: DS-2CD2347G2-L(U)
**Source Data (Hikvision):**
```json
{
    "model": "DS-2CD2347G2-L(U)",
    "name": "4 MP ColorVu Fixed Turret Network Camera",
    "specifications": {
        "resolution": "4 MP (2560 ? 1440)",
        "sensor": "1/1.8\" Progressive Scan CMOS",
        "lens": "2.8 mm, 4 mm, 6 mm fixed lens",
        "night_vision": "ColorVu: 24/7 colorful imaging",
        "compression": ["H.265+", "H.265", "H.264+", "H.264"],
        "power": "12 VDC ? 25%, PoE (802.3af)",
        "weather_rating": "IP67"
    },
    "features": ["ColorVu 3.0", "AcuSense 3.0", "Built-in microphone"],
    "price": 65.50
}
```

**Mapped Data (BY MB):**
```json
{
    "model_number": "DS-2CD2347G2-L(U)",
    "product_name": "Hikvision ColorVu 4MP Fixed Turret Camera",
    "manufacturer": "Hikvision",
    "category": "CCTV Camera",
    "resolution": "4 Megapixel (2560 ? 1440)",
    "sensor": "1/1.8\" Progressive Scan CMOS",
    "lens_options": ["2.8mm", "4mm", "6mm"],
    "night_vision": "Full-color 24/7 with built-in supplemental light",
    "special_features": [
        "Full-color 24/7 night vision",
        "AI-powered human/vehicle detection",
        "Built-in microphone for audio recording"
    ],
    "wholesale_price": 65.50,
    "retail_price": 97.29,
    "key_benefits": [
        "Clear footage in complete darkness",
        "Reduced false alarms with AI detection",
        "Professional installation included"
    ]
}
```

---

## ? Customization Options

### Adding New Manufacturers
1. Create new mapper class (e.g., `TP-LinkMapper`)
2. Implement mapping logic for new data structure
3. Add to main sync system
4. Update configuration

### Custom Field Mapping
Edit `config/field_mappings.json`:
```json
{
    "hikvision_to_bymb": {
        "model": "model_number",
        "name": "product_name",
        "specifications.resolution": "resolution",
        "specifications.sensor": "sensor"
    }
}
```

### Price Rules
Modify pricing calculation in `sync_system.py`:
```python
def calculate_retail_price(self, wholesale_price, category):
    if category == "Premium CCTV":
        markup = 0.40  # 40% for premium products
    else:
        markup = 0.35  # 35% standard
    
    return wholesale_price * (1 + self.vat_rate) * (1 + markup)
```

---

## ? Monitoring & Analytics

### Sync Reports
- **Products Updated** - Number of existing products modified
- **Products Created** - New products added to catalog  
- **Errors** - Failed updates with reasons
- **Price Changes** - Automatic price adjustments
- **Stock Updates** - Inventory level changes

### Alert System
- **Email notifications** for sync completion
- **Error alerts** for failed updates
- **Price change notifications** for significant changes
- **Stock level warnings** for low inventory

---

## ? Security & Data Protection

### Data Security
- **Encrypted connections** to all external APIs
- **Secure credential storage** in configuration
- **Audit logging** of all data changes
- **Backup verification** before updates

### Access Control
- **API key authentication** for external sources
- **Odoo user permissions** for database updates
- **Log file protection** with appropriate permissions
- **Configuration file encryption** for sensitive data

---

## ? Troubleshooting

### Common Issues

**1. API Connection Failed**
```
Error: Unable to connect to Hikvision API
Solution: Check internet connection and API status
Fallback: System will use CSV backup data
```

**2. Odoo Authentication Failed**
```
Error: Invalid Odoo credentials
Solution: Verify username/password in config
Check: Ensure user has product management permissions
```

**3. Data Mapping Errors**
```
Error: Unable to map product specifications
Solution: Check field_mappings.json configuration
Debug: Enable detailed logging for specific products
```

**4. Price Calculation Issues**
```
Error: Invalid wholesale price data
Solution: Verify price format in source data
Fallback: Use manual pricing from backup file
```

### Support Contact
- **Technical Issues:** support@by-mb.com
- **System Admin:** +973-66300033 (Press 0)
- **Emergency Updates:** Manual sync via Odoo admin panel

---

## ? Version History

- **v1.0 (June 21, 2025)** - Initial release with Hikvision support
- **v1.1 (Planned)** - TP-Link integration
- **v1.2 (Planned)** - EZVIZ support
- **v2.0 (Planned)** - Multi-manufacturer dashboard

---

## ? Implementation Support

### For Technical Setup
- **Email:** support@by-mb.com
- **Phone:** +973-66300033
- **Documentation:** GitHub repository wiki

### For Business Configuration
- **Pricing Rules:** sales@by-mb.com
- **Product Categories:** projects@by-mb.com
- **Custom Mappings:** info@by-mb.com

---

**Status:** Ready for Implementation  
**Dependencies:** Python 3.8+, Odoo 15+, stable internet connection  
**Maintenance:** Automated with manual oversight capability

*This system ensures your BY MB Consultancy website always displays the most current and accurate product information from manufacturers, maintaining your professional credibility while reducing manual update workload.*