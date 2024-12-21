# bugpage
This page is primarily used to test Github pages.
So this is my playground.

![typical usage](assets/images/typical.gif)

click download [CustomScan](CustomScan.policy)

In markdown syntax, at mark(@) is userlink.

goto repo: @gdgd009xcd

commit at mark sign test2

## how to use

1. Active Scan Input Vectors option panel<br>
   This is automatically called when you start active scannig after already installed default scanners.
   If this addon look like doing nothing, you should check:<br> [Tools->Options->Active Scan Input Vectors] option panel.<br>
   If nothing is enabled in this options panel, you may push<br>[Reset to factory defaults] button or check on individually.
   ![InputVectors](assets/images/activescaninputvectors.png)

2. Why does this scan hang at 37% on the scan progress gauge?<br>
   This is not this addon's problem.<br>
   Zaproxy's DOM XSS Active scanner rule(DomXssScanRule) plugin uses selenium to scan.<br>
   In ubuntu latest version, selenium may not work with the Firefox Snap Version(default).<br>
   Workarounds have many ways, so I can't explain all of them. but I can explain some of them.<br>
   You may change browser id in<br> [tools-options->rule configuration->rules.domxss.browserid] to avoid this problem.<br>
   Because this problem occurs on the Firefox Snap Version only.<br>
   value is "firefox", "firefox-headless"(default), "chrome", "chrome-headless".<br>
   I choosed "chrome-headless". but despite changed this value, you may need proper chrome browser and WebDriver for using DomXssScanRule. so this solution is to avoid hangup only and DomXssScanRule will still skipped in scanning.<br>

3. CustomScan.policy file<br>
If you have any doubts whether this scanner is actually being called, you can import the [CustomScan.policy](CustomScan.policy) file. This policy forces only the use of CustomScanRules when invoking active scan. using guide is follows:<br>

    1. download [CustomScan.policy](CustomScan.policy)
    1. select menu [Analyse->Scan Policy Manager->import], and load CustomScan.policy file.
    1. when you start scan, select policy [Custom Scan].

Information on how to use can be found at the following link: <BR>
[Basic Usage](https://github.com/gdgd009xcd/CustomActiveScanForZAP/wiki/1.0.-Basic-Usage)

## Author
### [gdgd009xcd](https://gdgd009xcd.github.io/)


