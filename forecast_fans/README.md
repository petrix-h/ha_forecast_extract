# Helpers

## 24h lowest temp parser
Create: 
- input_number to hold the lowest temp value
- input_datetime the datetime of the lowest value



## Auto fan

Create: 
- input_number min_temp_below_threshold 
- input_number hours_until_min_temp
- input_select auto_fan_state with options: IDLE, PREHEAT, HEAT, WAIT, MANUAL

The idea is that the select is a state machine: 
- idle = off
- preheat = on
- heat = on
- wait = off waiting for another condition like external temp sensor 
- MANUAL = controlled by other factors, script won't touch... 
