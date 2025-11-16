# Helpers

## 24h Forecast Parser
Create: 
- input_number.min_temp_next_24h - to hold the lowest temp value
- input_datetime.min_temp_24h_date_time - the datetime of the lowest value
- input_text.forecast_24h_data - stores complete 24h forecast as JSON

## Auto Fan State Machine

Create: 
- input_select.auto_fan_state with options: IDLE, PREHEAT, HEAT, WAIT, MANUAL


## State Machine Logic
- **IDLE** = fans off, normal operation
- **PREHEAT** = fans on, preparing for cold weather
- **HEAT** = fans on, actively heating based on current temperature
- **WAIT** = fans off, waiting for conditions (too cold to heat effectively)
- **MANUAL** = controlled by other factors, automation won't modify

## Preheating Logic
The automation now uses threshold crossing detection:
1. Scans 24h forecast to find when temperature first drops below the threshold (-3°C)
2. Starts preheating 4 hours before that threshold crossing

