Tags: #FOSS #LibreOffice

---

# Title
- __Description:__
- __Author:__ Kuan-Hsien Wu
- __Contact:__ jordankhwu@gmail.com
- __Date:__

# Table of Contents

# Context

## Refresh Font Cache
- After downloading new fonts, it is required to refresh the cache
    - `fc-cache -f -v`

## Microsoft Core Fonts
- In Ubuntu
    - `sudo apt install ttf-mscorefonts-installer`
- Contains
    ```
    Andale Mono
    Arial Black
    Arial (Bold, Italic, Bold Italic)
    Comic Sans MS (Bold)
    Courier New (Bold, Italic, Bold Italic)
    Georgia (Bold, Italic, Bold Italic)
    Impact
    Times New Roman (Bold, Italic, Bold Italic)
    Trebuchet (Bold, Italic, Bold Italic)
    Verdana (Bold, Italic, Bold Italic)
    Webdings
    ```
- But for most of the fonts from it, you can find a FOSS alternatives
- Reference
    - https://packages.debian.org/bullseye/ttf-mscorefonts-installer

## English Fonts FOSS Alternatives

| Proprietary     | FOSS             |
| :-------------: | :--------------: |
| Times New Roman | Liberation Serif |
| Arial           | Liberation Sans  |
| Courier         | Liberation Mono  |
| Calibri         | Carlito          |
| Cambria         | Caladea          |
- Reference
    - https://ask.libreoffice.org/t/calibri-and-cambria-fonts-in-libreoffice/3515

## Chinese Font Setting Cross-Libreoffice-and-MicrosoftOffice
- In Ubuntu, `/etc/fonts/conf.avail/30-cjk-aliases.conf` record how Chinese fonts are rendered
- For example:
    ```
    <!-- Aliases for Traditional Chinese Windows fonts -->
    <alias>
        <family>新細明體</family>
        <accept>
            <family>Noto Serif CJK TC</family>
            <family>AR PL UMing TW</family>
        </accept>
    </alias>
    ```
    - `<family>` tag: fonts that shows up in libreoffice
    - `<accept>` tag: fonts that are actually rendered from top to bottom
- You can easily modify this file to make sure that your documents are using the same font across platforms
- Reference
    - https://data.gov.tw/dataset/5961

## How to Change Default Chinese Font in Libreoffice
- Reference
    - https://ask.libreoffice.org/t/how-can-i-change-the-default-font-in-all-components-of-libreoffice-for-network-organisation-deployment/9570
