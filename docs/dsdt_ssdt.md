# Manual
- Collect DSDT.aml use opencore SysReport, configure in Misc->Debug->SysReport, and must use debug version of opencore. see https://dortania.github.io/Getting-Started-With-ACPI/ssdt-methods/ssdt-methods.html
- You can find DSDT.aml in your EFI partion, ACPI/DSDT-aml
- Decompile to get DSDT.dsl, Use iasl and Maciasl tools this repsitory provide, be sure you decompile success

    ./iasl -da -dl DSDT.aml SSDT*.aml

- Patch and compile SSDT
  
