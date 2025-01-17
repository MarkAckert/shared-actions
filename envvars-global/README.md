# Importing global environment variables

This action exports environment variables for the whole workflow to be used. It is suggested to be run at the very top of the workflow.

## Inputs
None

## Outputs
None

## Exported environment variables 
(global env vars - for subsequent workflow steps to consume)
- Environment variables as defined in [envvars.env](./envvars.env)
- JSON files to be transformed to String then exported as environment variables 
<br /><br />

## Example usage
```
uses: zowe-actions/shared-actions/envvars-global@main
```
#### Note:
- If you wish to add more global environment variables, please add them in [envvars.env](./envvars.env)\
  Comments starting with `#` and blank lines are allowed for easy reading, they will be sanitized during processing.
- If you wish to export more JSON file, add the file in current directory, then in [action.yml](./action.yml), do
  ```
  echo '{VARIABLE_NAME}<<EOF' >> $GITHUB_ENV
  cat {filename}.json >> $GITHUB_ENV
  echo 'EOF' >> $GITHUB_ENV
  ```
