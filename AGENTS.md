# AGENTS.md

## Build/Lint/Test Commands
This is a Home Assistant configuration repository with YAML automations and Jinja2 templates. No traditional build/test commands exist.

## Code Style Guidelines

### YAML Files (.yaml)
- Use 2-space indentation
- Follow Home Assistant automation structure: alias, description, triggers, conditions, actions
- Use descriptive aliases and entity IDs
- Include metadata: {} for actions
- Use proper YAML quoting for templates with special characters

### Jinja2 Templates (.j2)
- Use {%- for whitespace control
- Add comments explaining complex logic
- Use descriptive variable names
- Clamp values with if/elif/else for safety
- Round numerical outputs appropriately

### Naming Conventions
- Entity IDs: snake_case with domain prefix (sensor.temperature_humidity_sensor_e303_temperature)
- Input helpers: descriptive names with type prefix (input_number.min_temp_below_threshold)
- State options: UPPERCASE (IDLE, PREHEAT, HEAT, WAIT, MANUAL)

### Error Handling
- Use default values in templates (float(0))
- Include conditions to prevent invalid state transitions
- Use numeric_state conditions with for: duration
- Handle MANUAL state to prevent automation interference