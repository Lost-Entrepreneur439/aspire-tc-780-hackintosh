macOS Ventura EFI for the Acer Aspire TC-780 using OpenCore. I will try to keep this EFI up to date with the latest OpenCore and kexts

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7f6c8e75-eae7-4870-83ac-1063a1590056" />

# WARNING! SMBIOS DETAILS ARE NOT INCLUDED IN THE CONFIG.PLIST.
You will have to use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate a **iMac18,1** SMBIOS for your system, and add them to the config.plist.

## Other macOS versions?
No. Ventura is the latest supported by iMac18,1, so it's all I'll ever support. If you want a different version, feel free to fork this repo to modify it for whatever version you want. Do note newer versions will likely require OCLP.

## System specs
Do note if your hardware differs, while unlikely, you may have issues.
- CPU: Intel Core i3-7100
- GPU: Intel HD Graphics 630
- Chipset: Intel H110
- Audio Codec: Realtek ALC662
- WiFi: Intel Dual-Band Wireless-AC 3168
- Ethernet: Realtek RTL8111
- Disk: Western Digital Blue 1TB 3.5" 7200RPM HDD

## Issues:
- VGA does not work. While it should be possible to get it to work since Kaby Lake converts to DP internally, I've had no luck
- The system panics upon waking from sleep. This is a known issue with systems using the HD 630, and the only way to fix it is by installing a supported AMD GPU.

If you notice any other problems, please open an issue (or pull request if you have a fix)

### BIOS settings
If you do not set these BIOS settings, macOS will **not** boot.
- Advanced -> Integrated Peripherals -> Onboard SATA Mode -> AHCI
- Authentication -> Secure Boot -> Disabled
- Boot Options -> Launch CSM -> Never
