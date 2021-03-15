Hach HQ Series Firmware manifest
================================

This repository contains the manifest files for the Hach HQ Series portable meter firmware.

Building HQ Series Firmware
---------------------------

To download HQ Series Firmware, you need the repo tool.

Follow these steps to install HQ Series Firmware:

1. Download repo to a directory within your path and add execution permissions.

    ```
    $ sudo curl -o /usr/local/bin/repo http://commondatastorage.googleapis.com/git-repo-downloads/repo
    $ sudo chmod a+x /usr/local/bin/repo
    ```

2. Create an installation folder with user write permissions; for example,
    `~/hqseries-bsp` and navigate to that folder.

    ```
    $ mkdir ~/hqseries-bsp
    $ cd ~/hqseries-bsp
    ```

3. Use repo to download HQ Series Firmware.

    ```
    $ repo init -u https://github.com/HachCompany-HQSeries/hqseries-bsp
    $ repo sync -j8 --no-repo-verify
    ```

4. Build the firmware image.

    ```
    $ mkdir build && cp build
    $ source ../mkproject.sh -m meta-r1701-public -p r1701
    $ bitbake hqseries-portable-image
    ```
