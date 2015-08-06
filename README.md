# niminifiles
Simple ini file reader in Nim

This simple module allows you to read in an inifile and quickly access it's key values via inifile.find.
Originally I had used a variant of this with parsecfg, but it doesn't like sloppy ini files where string values aren't quoted or something else pops the parser.

Example of use:

```nimrod
if loadIni(ini, "Config.ini"):
  connection.host = ini.find("database", "hostname")
  connection.database = ini.find("database", "database")
  connection.integratedSecurity = ini.find("database", "winauth") == "1"
else:
  echo "File not found or no keys found"
```
