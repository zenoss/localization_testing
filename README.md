# Testing Localization
Contains test modules and scripts for testing language localization with the Microsoft Windows ZenPack

Performance counters in Windows are language specific.  See the PowerShell scripts in the powershell folder for assistance in finding localized counter names.

## Getting Started
To test polling localized counters, 
* Start with creating a subclass below */Server/Microsoft/Windows*.
* Next, make copies of the existing monitoring templates in this class.
* Replace the counters in the datasources with the non-English equivalents.
* You *must* also update the zWinRMLocale property with the appropriate culture of your service account.  For example, native French locale would be 'fr-FR'.  The full list of cultures can be found at https://msdn.microsoft.com/en-us/library/ee825488(v=cs.20).aspx.

## Notes
Some languages, such as French, contain elided words in performance counters.  e.g. ''d’utilisation''.  Be sure to check that the unicode apostrophe is being used in these counter names.
