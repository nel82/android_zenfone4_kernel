obj-$(CONFIG_X86_INTEL_MID) += intel-mid.o
obj-$(CONFIG_X86_INTEL_MID)	+= intel_mid_vrtc.o
obj-$(CONFIG_EARLY_PRINTK_INTEL_MID)	+= early_printk_intel_mid.o
obj-$(CONFIG_INTEL_MID_PSTORE_RAM) += intel_mid_pstore_ram.o

# SPID code
obj-y += spid.o

# SFI specific code
obj-$(CONFIG_SFI) += intel_mid_sfi.o
obj-y += spc_pwr_set.o
ifeq ($(ASUS_BT_CHIP_NAME), BCM2076)
    KBUILD_CFLAGS += -DFOR_2076
endif

ifeq ($(ASUS_BT_CHIP_NAME), BCM4343)
    KBUILD_CFLAGS += -DFOR_4343
endif

ifeq ($(ASUS_BT_CHIP_NAME), BCM43341)
    KBUILD_CFLAGS += -DFOR_43341
endif

ifneq (,$(filter FE171CG ME171C,$(ASUS_PROJECT)))
        KBUILD_CFLAGS += -DBT_USE_UART3
endif			

# platform configuration for board devices
obj-y += device_libs/

# SoC specific files
obj-$(CONFIG_X86_INTEL_MID) += mfld.o mrfl.o
obj-$(CONFIG_X86_WANT_INTEL_MID) += vlv2.o intel_mid_pcihelpers.o
obj-$(CONFIG_X86_INTEL_MID) += intel_mid_scu.o

# BOARD files
obj-$(CONFIG_X86_INTEL_MID) += board.o

# PMU driver
obj-$(CONFIG_ATOM_SOC_POWER) += intel_soc_pmu.o intel_soc_pm_debug.o intel_soc_dump.o
obj-$(CONFIG_REMOVEME_INTEL_ATOM_MDFLD_POWER) += intel_soc_mdfld.o intel_soc_mdfld_clv_common.o
obj-$(CONFIG_REMOVEME_INTEL_ATOM_CLV_POWER) += intel_soc_clv.o intel_soc_mdfld_clv_common.o
obj-$(CONFIG_REMOVEME_INTEL_ATOM_MRFLD_POWER) += intel_soc_mrfld.o

# pci acpi quirk driver
obj-$(CONFIG_INTEL_SOC_PMC) += intel_soc_pci_acpi_quirk.o

# Debug features driver
obj-$(CONFIG_INTEL_DEBUG_FEATURE) += intel_soc_debug.o
