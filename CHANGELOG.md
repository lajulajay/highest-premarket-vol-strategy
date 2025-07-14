# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/) and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [2.1.0] – 2025-01-27

### Added
- **Label Display Controls**: New options to show/hide level labels and pattern recognition labels
- **Label Size Options**: Choose between tiny, small, or normal label sizes for different chart timeframes
- **Streamlined Visual Experience**: Reduced chart crowding with better label positioning
- **Enhanced Parameter Organization**: Reorganized inputs into logical groups (volume, pattern, display)
- **Visual Customization**: Flexible display options for crowded charts, especially 1-minute timeframes
- **Advanced Consolidation Detection**: Bar-to-bar range comparison instead of session min/max analysis
- **Consecutive Small Ranges**: Detects consolidation when enough consecutive bars show small ranges
- **Post-Move Analysis**: Only considers bars after the strong move for consolidation detection

### Changed
- **Default Label Settings**: Pattern recognition labels disabled by default to reduce visual clutter
- **Parameter Grouping**: Organized inputs into Volume Analysis, Pattern Detection, and Display Options sections
- **Label Positioning**: Improved spacing and positioning for better readability
- **User Experience**: More intuitive controls for visual customization
- **Consolidation Detection Logic**: Switched from session range analysis to bar-to-bar comparison for more accurate pattern detection

### Technical Improvements
- **Variable Management**: Better handling of label size enumeration across different sections
- **Error Prevention**: Fixed undeclared identifier issues with proper variable declarations
- **Code Organization**: Cleaner separation of display logic from core functionality
- **Performance**: Optimized label rendering and reduced redundant calculations
- **Consolidation Algorithm**: More precise detection using consecutive small bar-to-bar ranges

---

## [2.0.0] – 2025-01-27

### Fixed
- **Volume Analysis**: Now properly compares pre-market volume to historic highest volume (was missing entirely)
- **Pattern Detection**: Correctly identifies single strong move up followed by consolidation (was using session high/low instead of consolidation levels)
- **Level Marking**: Uses consolidation high/low (candle bodies) instead of session extremes (was using wicks)
- **Breakout Capture**: Captures actual breakout price instead of pre-market high (was setting breakout price incorrectly)
- **Single Move Validation**: Ensures only one strong move occurs (was allowing multiple moves)

### Added
- **Historic Volume Comparison**: Compares current pre-market volume to historic highest with configurable threshold
- **Volume Requirement Integration**: Pattern only triggers when volume criteria is met
- **Precise Consolidation Detection**: Identifies tight consolidation after strong initial move
- **"FIRST BREAKOUT" Annotation**: Clear labeling of actual breakout price
- **Enhanced Target Descriptions**: More descriptive labels for 5% gain, 1:3 risk:reward, and measured move
- **Improved Pattern Recognition**: More accurate retest, bull flag, and ABCD pattern detection
- **Volume Display**: Shows volume vs historic highest ratio in info table

### Changed
- **Parameter Organization**: Reorganized inputs into logical groups (volume, pattern, display)
- **Default Values**: Updated consolidation threshold from 2.0% to 1.5% for tighter consolidation
- **Alert Messages**: More descriptive alert messages for pattern and breakout detection
- **Visual Enhancements**: Improved breakout candle highlighting and table display

### Technical Improvements
- **Code Structure**: Better organized sections with clear step-by-step implementation
- **Variable Management**: Proper reset of variables at start of new trading day
- **Error Prevention**: Added safeguards to prevent invalid pattern detection
- **Performance**: Optimized calculations and reduced redundant operations

---

## [1.0.0] – 2025-06-19

### Added
- First public release of Highest Pre-market Volume Strategy
- Detects pre-market high/low using 1-minute candles (04:00–09:30 ET)
- Flags breakouts after 9:30 AM
- Plots 5% target line above breakout
- Optional 1:3 Risk:Reward annotation

### Notes
- Designed for use on 1-minute charts with extended trading hours enabled