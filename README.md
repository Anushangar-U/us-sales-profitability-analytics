# US Sales and Profitability Analytics Suite

A comprehensive Power BI analytics solution designed to provide deep insights into US sales performance, profitability metrics, and regional trends.
https://github.com/Anushangar-U/us-sales-profitability-analytics/blob/main/US%20Sales%20and%20Profitability%20Analytics%20Suite.pdf
## 📋 Overview

The **US Sales and Profitability Analytics Suite** is an enterprise-grade Power BI project that enables data-driven decision-making through interactive dashboards and detailed analytics. The suite provides a 360-degree view of sales operations, profit margins, and product performance across different regions.

### Key Features
- **Multi-page Interactive Dashboards** with real-time analytics
- **Advanced DAX Calculations** for year-over-year growth, moving averages, and profitability metrics
- **Dynamic Filtering** with Top N product selector and dimension switcher
- **Time Intelligence** capabilities for period-over-period comparisons
- **Regional Performance Tracking** with drill-down capabilities
- **Professional Theme** with light blue background design

---

## 📊 Report Pages

### 1. **Executive Summary** (Default Page)
The main landing page providing a high-level overview of key business metrics and KPIs.

### 2. **Sales Trends**
Focuses on sales performance trends with:
- Monthly sales analysis
- Year-over-year sales growth comparison
- 30-day sales moving average
- Trend visualization by year

### 3. **Regional Detail**
Provides detailed insights by region including:
- Regional revenue distribution
- Region-specific profitability metrics
- Cross-regional comparisons
- Regional performance tracking

### 4. **Product Analysis**
Deep-dive into product-level performance:
- Top N products by sales (dynamic selector)
- Product-level profitability
- Sales targets vs. actual performance
- Product ranking and performance metrics

---

## 🏗️ Data Model Architecture

### Tables

#### **Superstore** (Fact Table)
Main transactional data containing:
- Order information (Order_ID, Order_Date, Ship_Date)
- Sales metrics (Sales, Profit, Quantity)
- Customer details (Region, Product_Name, Category)
- Key fields for dimensional analysis

#### **DimDate** (Dimension Table)
Date dimension providing:
- Calendar attributes (Date, Month, Year, Month_Name)
- Used for time-based filtering and analysis
- Supports month-to-date and year-over-year calculations

#### **Supporting Tables**
- **Top N Selector**: Dynamic parameter table for product ranking filters
- **Dimension Switcher**: Utility table for dynamic dimension selection

### Relationships
- **Superstore → DimDate** (via Order_Date) - Main analytical relationship
- **Superstore → LocalDateTable** (via Ship_Date) - Shipping date tracking
- **DimDate → LocalDateTable** - Date hierarchy relationships

---

## 📈 Key Measures & KPIs

### Core Metrics
| Measure | Description |
|---------|-------------|
| **Total Sales** | Sum of all sales revenue |
| **Total Profit** | Sum of all profit amounts |
| **Total Orders** | Distinct count of orders |
| **Avg Order Value** | Average value per order |
| **Profit Margin** | Profit as percentage of sales |

### Time Intelligence Measures
| Measure | Description |
|---------|-------------|
| **Year-over-Year Sales Growth** | Sales growth compared to previous year |
| **Months to Date Sales (MTD)** | Cumulative sales for current month |
| **Sales 30-Day Average** | 30-day moving average of daily sales |
| **Sales Previous Year** | Prior year sales for comparison |

### Advanced Analytics
| Measure | Description |
|---------|-------------|
| **Product Rank** | Ranking of products by sales (Dense ranking) |
| **Top N Products** | Filter for displaying top N products dynamically |
| **Sales Target** | Target sales at 110% of previous year |
| **Best Month Label** | Dynamic label for best performing month |
| **Trend Title** | Dynamic title showing year and YoY growth |
| **Selected Region Title** | Dynamic title for selected region |

---

## 🔧 Project Structure

```
US Sales and Profitability Analytics Suite.pbip
├── US Sales and Profitability Analytics Suite.Report/
│   ├── definition.pbir
│   ├── definition/
│   │   ├── report.json
│   │   ├── pages/
│   │   │   ├── bd89f6047788d81cf4fa/     # Sales Trends
│   │   │   ├── cfb108478302ff82fe18/     # Regional Detail
│   │   │   ├── 6d2cd06ca001e9340c36/     # Product Analysis
│   │   │   └── dd33866138a4044ae7be/     # Executive Summary
│   │   └── bookmarks/                    # Report bookmarks/views
│   └── StaticResources/
│       └── BaseThemes/
│           └── CY26SU02.json
└── US Sales and Profitability Analytics Suite.SemanticModel/
    ├── definition.pbism
    ├── definition/
    │   ├── model.tmdl
    │   ├── database.tmdl
    │   ├── relationships.tmdl
    │   ├── cultures/
    │   └── tables/
    │       ├── Superstore.tmdl           # Fact table
    │       ├── DimDate.tmdl              # Date dimension
    │       ├── Top N Selector.tmdl       # Dynamic parameter
    │       └── Dimension Switcher.tmdl   # Dynamic switcher
    └── diagramLayout.json
```

---

## 🚀 Getting Started

### Prerequisites
- Power BI Desktop (latest version recommended)
- Microsoft Power BI Premium or Power BI Pro license
- Read access to the Power BI project files

### Opening the Project
1. Open Power BI Desktop
2. Navigate to **File → Open** and select `US Sales and Profitability Analytics Suite.pbip`
3. Wait for the semantic model to load
4. Start exploring the interactive dashboards

### Connecting Data
The project references a **Superstore** data source. Ensure the connection is properly configured:
1. Go to **Home → Transform Data** in Power BI Desktop
2. Configure the data source connection if prompted
3. Refresh the data to load the latest information

---

## 📌 Usage Guide

### Navigation
- Use the **page tabs** at the bottom to navigate between different analytics views
- Each page is self-contained with its own visualizations and filters

### Filtering & Interactivity
- **Dynamic Filters**: Use the Top N Selector to view top products (1-10)
- **Regional Filtering**: Click on regions to drill down into regional data
- **Date Filters**: Select date ranges using the date slicer on each page
- **Dimension Switcher**: Toggle between different dimensions for analysis

### Exporting & Sharing
- **Export Charts**: Right-click on any visual to export as image or PDF
- **Share Reports**: Use Power BI's sharing features to distribute reports to stakeholders
- **Bookmarks**: Create report bookmarks for specific views and insights

---

## 🔍 Advanced Features

### Dynamic Titles
The suite includes intelligent dynamic titles that update based on selections:
- Trend Title shows "Select a specific year to see YoY Growth" or displays YoY metrics
- Selected Region Title displays the currently selected region

### Top N Analysis
Filter and analyze the top N products dynamically:
- Adjust the selector to view top 1, 5, 10, or custom number of products
- Automatically ranks products by sales volume

### Time-Based Analytics
- **Month-to-Date (MTD)**: Monitor month-to-date performance
- **30-Day Average**: Track short-term trends with moving averages
- **Year-over-Year**: Compare current performance against prior years
- **SAMEPERIODLASTYEAR**: Automatically aligned period comparisons

---

## 📊 Data Refresh & Maintenance

### Refresh Schedule
Configure Power BI to automatically refresh the data:
1. Open the Power BI Service
2. Navigate to the dataset settings
3. Set an appropriate refresh schedule (daily/hourly recommended)

### Data Quality
- Monitor data accuracy regularly
- Verify that all date relationships are maintained
- Check for null values in critical fields

---

## 🎨 Customization

### Themes
The project includes:
- **CY26SU02**: Custom theme with professional styling
- **Storm**: Built-in theme option

To apply or modify themes:
1. Go to **View → Themes** in Power BI Desktop
2. Select the desired theme
3. Customize colors, fonts, and styling as needed

### Adding New Visuals
1. Select the page where you want to add a visualization
2. Choose visual type from the **Visualizations** pane
3. Drag and drop fields from the data model
4. Configure formatting and interactions

---

## 📝 Documentation

### DAX Formulas
All key DAX measures are documented with:
- Clear formula logic
- Purpose and use cases
- Supporting comments

### Model Documentation
- Relationship cardinality is properly configured
- All calculated measures are well-defined
- Culture settings support internationalization (en-US)

---

## 🤝 Contributing

### Making Changes
1. Create a copy for testing before making changes to production
2. Document all new measures or tables added
3. Test all relationships and formulas thoroughly
4. Maintain consistency with existing naming conventions

### Naming Conventions
- **Measures**: Use PascalCase (e.g., `Total Sales`, `Profit Margin`)
- **Columns**: Use snake_case for raw data columns (e.g., `Order_ID`, `Ship_Date`)
- **Tables**: Use PascalCase (e.g., `Superstore`, `DimDate`)

---

## 🐛 Troubleshooting

### Common Issues

| Issue | Solution |
|-------|----------|
| Data not refreshing | Check data source connectivity and Power BI Service settings |
| Slow performance | Optimize visuals, reduce data filters, consider aggregations |
| Blank pages | Verify data relationships and measure calculations |
| Filter not working | Check filter column relationships in the data model |

### Performance Tips
- Use row-level security (RLS) for large datasets
- Limit the number of visuals per page
- Use aggregated tables for complex calculations
- Cache frequently used calculations

---

## 📞 Support & Contact

For issues, questions, or enhancements:
- Contact the BI team
- Review Power BI documentation at https://docs.microsoft.com/power-bi/
- Check the project repository for updates

---

## 📄 License & Attribution

This Power BI project uses sample Superstore data for demonstration purposes.

---

## 📅 Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-06-19 | Initial release with 4 main pages and comprehensive analytics |

---

## 🌟 Key Insights

This analytics suite enables:
- ✅ Real-time sales performance monitoring
- ✅ Profitability tracking by region and product
- ✅ Trend identification with year-over-year comparisons
- ✅ Dynamic top-N product analysis
- ✅ Month-to-date and rolling average metrics
- ✅ Interactive drill-down capabilities for detailed exploration

**Start exploring your data today!**
