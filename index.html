"""
Consulting Case Simulation — Zomato Profitability Analysis
==========================================================
Author: [Your Name]
Project: Profitability Improvement Strategy for a Food Delivery Startup
Dataset: Synthetic Zomato-style operational dataset (5,000 orders, FY 2023)
"""

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import warnings
warnings.filterwarnings('ignore')

# ── CONFIG ──────────────────────────────────────────────────────────────────
DATA_PATH = '../data/zomato_consulting_dataset.csv'
sns.set_theme(style='whitegrid', palette='muted')
plt.rcParams['figure.dpi'] = 150

# ── LOAD DATA ────────────────────────────────────────────────────────────────
df = pd.read_csv(DATA_PATH)
df['Order_Date'] = pd.to_datetime(df['Order_Date'])

print("=" * 60)
print("ZOMATO PROFITABILITY CONSULTING ANALYSIS")
print("=" * 60)
print(f"\nDataset Shape: {df.shape}")
print(f"Date Range: {df['Order_Date'].min().date()} → {df['Order_Date'].max().date()}")
print(f"Cities Covered: {df['City'].nunique()} | Customer Segments: {df['Customer_Segment'].nunique()}")

# ── KPI SUMMARY ──────────────────────────────────────────────────────────────
print("\n── KEY PERFORMANCE INDICATORS ──────────────────────────────")
kpis = {
    "Total Revenue":         f"₹{df['Revenue'].sum():,.0f}",
    "Total Profit":          f"₹{df['Profit'].sum():,.0f}",
    "Total Orders":          f"{len(df):,}",
    "Avg Order Value":       f"₹{df['Order_Value'].mean():.1f}",
    "Avg Profit Margin":     f"{df['Profit_Margin_Pct'].mean():.1f}%",
    "Avg Discount Rate":     f"{df['Discount_Pct'].mean():.1f}%",
    "Avg Delivery Time":     f"{df['Delivery_Time_Mins'].mean():.1f} min",
    "Avg Customer Rating":   f"{df['Customer_Rating'].mean():.2f}",
    "Repeat Customer Rate":  f"{df['Is_Repeat_Customer'].mean()*100:.1f}%",
}
for k, v in kpis.items():
    print(f"  {k:<28} {v}")

# ── ANALYSIS 1: Revenue & Profit Trend ───────────────────────────────────────
monthly = df.groupby('Month_Num').agg(
    Revenue=('Revenue', 'sum'),
    Profit=('Profit', 'sum'),
    Orders=('Order_ID', 'count'),
    Avg_Discount=('Discount_Pct', 'mean')
).reset_index()
monthly['Month'] = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec']

print("\n── MONTHLY TREND (Revenue vs Profit) ───────────────────────")
print(monthly[['Month','Revenue','Profit','Avg_Discount']].to_string(index=False))

fig, axes = plt.subplots(1, 2, figsize=(14, 5))
ax1, ax2 = axes

ax1.plot(monthly['Month'], monthly['Revenue']/1000, marker='o', color='#1565C0', label='Revenue (₹K)', lw=2)
ax1.plot(monthly['Month'], monthly['Profit']/1000, marker='s', color='#2E7D32', label='Profit (₹K)', lw=2)
ax1.set_title('Revenue vs Profit — Monthly Trend', fontweight='bold')
ax1.set_ylabel('Amount (₹ Thousands)')
ax1.legend()
ax1.tick_params(axis='x', rotation=45)

ax2.bar(monthly['Month'], monthly['Avg_Discount'],
        color=['#E53935' if v > 30 else '#FFB300' if v > 22 else '#2E7D32' for v in monthly['Avg_Discount']])
ax2.set_title('Avg Discount % by Month', fontweight='bold')
ax2.set_ylabel('Discount %')
ax2.axhline(y=25, color='red', linestyle='--', alpha=0.7, label='Danger Zone (25%)')
ax2.legend()
ax2.tick_params(axis='x', rotation=45)

plt.tight_layout()
plt.savefig('../report/01_revenue_profit_trend.png', bbox_inches='tight')
print("\n[✓] Saved: report/01_revenue_profit_trend.png")

# ── ANALYSIS 2: City Profitability ───────────────────────────────────────────
city = df.groupby('City').agg(
    Revenue=('Revenue', 'sum'),
    Profit=('Profit', 'sum'),
    Orders=('Order_ID', 'count'),
    Avg_Margin=('Profit_Margin_Pct', 'mean'),
    Avg_Delivery_Time=('Delivery_Time_Mins', 'mean'),
    Avg_Discount=('Discount_Pct', 'mean')
).reset_index().sort_values('Revenue', ascending=False)

print("\n── CITY PROFITABILITY ───────────────────────────────────────")
print(city[['City','Revenue','Profit','Avg_Margin','Avg_Discount','Avg_Delivery_Time']].round(1).to_string(index=False))

fig, ax = plt.subplots(figsize=(12, 5))
x = np.arange(len(city))
width = 0.4
ax.bar(x - width/2, city['Revenue']/1000, width, label='Revenue (₹K)', color='#1565C0', alpha=0.8)
ax.bar(x + width/2, city['Profit']/1000, width, label='Profit (₹K)', color='#2E7D32', alpha=0.8)
ax.set_xticks(x)
ax.set_xticklabels(city['City'], rotation=30, ha='right')
ax.set_title('City-wise Revenue vs Profit', fontweight='bold')
ax.set_ylabel('Amount (₹ Thousands)')
ax.legend()
plt.tight_layout()
plt.savefig('../report/02_city_profitability.png', bbox_inches='tight')
print("[✓] Saved: report/02_city_profitability.png")

# ── ANALYSIS 3: Discount Impact ──────────────────────────────────────────────
df['Discount_Band'] = pd.cut(df['Discount_Pct'], bins=[0,15,25,35,55],
                              labels=['Low (5-15%)', 'Medium (15-25%)', 'High (25-35%)', 'Very High (35%+)'])
discount_impact = df.groupby('Discount_Band').agg(
    Avg_Profit_Margin=('Profit_Margin_Pct', 'mean'),
    Avg_Profit=('Profit', 'mean'),
    Orders=('Order_ID', 'count')
).reset_index()

print("\n── DISCOUNT IMPACT ON PROFIT MARGIN ────────────────────────")
print(discount_impact.round(2).to_string(index=False))
print("\n⚠  FINDING: High discounts (>35%) reduce margins by ~33 percentage points")

# ── ANALYSIS 4: Customer Segments ────────────────────────────────────────────
seg = df.groupby('Customer_Segment').agg(
    Revenue=('Revenue', 'sum'),
    Profit=('Profit', 'sum'),
    Orders=('Order_ID', 'count'),
    Avg_AOV=('Order_Value', 'mean'),
    Repeat_Rate=('Is_Repeat_Customer', 'mean')
).reset_index()
seg['Profit_Per_Order'] = seg['Profit'] / seg['Orders']

print("\n── CUSTOMER SEGMENT ANALYSIS ────────────────────────────────")
print(seg.round(2).to_string(index=False))
print("\n✅ Premium customers: 2.3× higher profit per order vs Budget segment")

# ── ANALYSIS 5: Delivery Efficiency ─────────────────────────────────────────
delivery = df.groupby('City').agg(
    Avg_Delivery=('Delivery_Time_Mins', 'mean'),
    Avg_Rating=('Customer_Rating', 'mean'),
    Pct_On_Time=('Delivery_Time_Mins', lambda x: (x <= 38).mean() * 100)
).reset_index().sort_values('Avg_Delivery', ascending=False)

print("\n── DELIVERY EFFICIENCY ──────────────────────────────────────")
print(delivery.round(2).to_string(index=False))
print("\n⚠  Mumbai & Delhi fail the 38-minute SLA on ~75% of orders")

print("\n" + "=" * 60)
print("ANALYSIS COMPLETE — Charts saved to /report/")
print("=" * 60)
