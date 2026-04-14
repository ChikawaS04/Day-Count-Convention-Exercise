Day Count Exercise
A Java implementation of common day count conventions used in fixed income and derivatives pricing.
Overview
Day count conventions determine how the time between two dates is expressed as a year fraction. These calculations are fundamental to bond pricing, swap valuation, and interest accrual across financial markets.
This project implements four industry-standard conventions:

ACT/360 — actual days divided by 360
ACT/365 — actual days divided by 365
30/360 US — assumes 30-day months and 360-day year (Bond Basis)
ACT/ACT ISDA — actual days divided by actual days in year, handling leap years correctly

Project Structure
src/main/java/com/examplecode/daycount/
├── DayCountConvention.java    # Interface defining the contract
├── DayCountFactory.java       # Factory for obtaining convention instances
├── Act360.java                # ACT/360 implementation
├── Act365.java                # ACT/365 implementation
├── Thirty360US.java           # 30/360 US Bond Basis implementation
└── ActActISDA.java            # ACT/ACT ISDA implementation
Usage
javaDayCountConvention dcc = DayCountFactory.getConvention("ACT/360");

LocalDate start = LocalDate.of(2024, 1, 15);
LocalDate end = LocalDate.of(2024, 7, 15);

double yearFraction = dcc.yearFraction(start, end);
Requirements

JDK 25
Maven
IntelliJ IDEA (recommended)

Key Takeaways

Strategy pattern for swappable algorithms behind a common interface
Factory pattern for decoupling client code from concrete implementations
java.time API for date arithmetic (ChronoUnit, Year.isLeap)
Defensive validation with fail-fast exceptions
