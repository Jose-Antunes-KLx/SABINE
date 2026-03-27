# SABINE


## Name
SABINE - Sage Bank Integration Exchange 

## Description
A Python-based framework for processing flat file bank statement formats (AFB120, SWIFT MT940, ISO20022 camt.053). The system is architected with modular components for **data integrity validation**, **duplicate transaction detection**, and **automated Sage Banque format conversion**, ensuring seamless integration with downstream financial applications.  

Key architectural features include:  
- **Maintainability**: Clear separation of parsing, validation, and conversion layers, enabling easier updates and format extensions.  
- **Stability**: Robust error-handling and logging mechanisms to ensure predictable behavior under high-volume daily operations.  
- **Efficiency**: Optimized routines for batch processing and conversion, reducing latency in daily reconciliation workflows.  
- **Extensibility**: Designed to accommodate additional banking formats and conversion targets with minimal reconfiguration.  

This solution provides a more maintainable, stable, and efficient approach to handling the daily conversion of bank statement files, reducing operational overhead while improving reliability across financial data pipelines.  


Python-based conversion system with the following components:

1. **Core Conversion Engine**:
-	Python modules for parsing and transforming each bank data format
-	including AFB120, SWIFT MT940, ISO20022 camt.053 formats, also scalable to other formats
-	Configurable mapping definitions to handle format variations
-	Error handling and validation at each conversion step
-	Preservation of current account filtering logic
2. **Account Filtering System**:
-	Maintain current rules for filtering out restricted or unwanted accounts
-	Configurable block-list/allow-list management
-	Rule-based processing to determine which accounts to process
3. **Duplicate Detection System**:
-	SHA-256 hashing implementation to identify duplicate bank statements
-	Fingerprinting logic for transaction records
-	Configurable duplicate handling (logging, skipping, or flagging)
4. **Data Integrity Validation**:
-	Date sequence verification to ensure chronological order
-	Balance reconciliation between statement totals and transaction line items
-   Transaction sequence reference gap detection
-	Configurable error handling for data integrity issues (flag, reject, or report)
5. **File Distribution System**:
-	Maintain existing file distribution rules to target systems
-	Configurable routing based on account types and data characteristics
-	Compatibility with current downstream systems
6. **Processing History Database**:
-	SQLite3 database technology for persistent storage of processing metadata
-	Optimized database schema for fast hash lookups with minimal performance impact
-	Storage of account numbers, hash values, processing dates, and results
-	Performance-optimized query patterns with proper indexing
7. **Automated Reporting & Alerting System**:
-	Daily processing summary reports (text, xmlx, pdf) sent via email
-	Real-time alerts for critical errors or validation failures
-	Configurable notification rules based on event severity
-	Detailed status reports with processing statistics
-	Visualization of key metrics (future release)
8. **Unified Command Interface**:
-	Single entry point replacing multiple batch files
-	Command-line options for different processing modes
-	Logging and reporting capabilities
9. **Process Automation**:
-	Scheduled execution via external tasks
-	Error notification and logging system


## Authors and acknowledgment
José Antunes (jose.antunes@klx.pt)


## Project status
- SABINE project has been validated from architectural, planning, and budget perspectives.
- Phase 1 development is complete. 
- Phase 2 start planned for Q1 2026 (budget approved).
- Reconfiguration of Phase 1 development into executable format, due to Python installation limitations on Production server.
- Awaiting for MEP date.
