## About

dcm_qa_deident is a simple DICOM to NIfTI validator script and dataset. This repository is similar to [dcm_qa](https://github.com/neurolabusc/dcm_qa), but validates the detection of [https://github.com/bids-standard/bids-specification/issues/1709](deidentification methods) that have now been added to the [BIDS format](https://github.com/bids-standard/bids-specification/pull/1772).

Looking at a DICOM header with dcmdump or gdcmdump will reveal that the DICOM images have de-identification details that can be preserved:

```
(0012,0064) SQ (Sequence with undefined length)                 # u/l,1 De-identification Method Code Sequence
  (fffe,e000) na (Item with undefined length)
    (0008,0100) SH [113102]                                     # 6,1 Code Value
    (0008,0102) SH [DCM ]                                       # 4,1 Coding Scheme Designator
    (0008,0103) SH [01]                                         # 2,1 Coding Scheme Version
    (0008,0104) LO [Clean Recognizable Visual Features Option ] # 42,1 Code Meaning
  (fffe,e00d)
  (fffe,e000) na (Item with undefined length)
    (0008,0100) SH [replace_recognizable]                       # 20,1 Code Value
    (0008,0102) SH [mri_reface]                                 # 10,1 Coding Scheme Designator
    (0008,0103) SH [0.3.4 ]                                     # 6,1 Coding Scheme Version
    (0008,0104) LO [Replace face, ears, and artifacts in air]   # 40,1 Code Meaning
  (fffe,e00d)
  (fffe,e000) na (Item with undefined length)
    (0008,0100) SH [113100]                                     # 6,1 Code Value
    (0008,0102) SH [DCM ]                                       # 4,1 Coding Scheme Designator
    (0008,0104) LO [Basic Application Confidentiality Profile ] # 42,1 Code Meaning
  (fffe,e00d)
  (fffe,e000) na (Item with undefined length)
    (0008,0100) SH [113107]                                     # 6,1 Code Value
    (0008,0102) SH [DCM ]                                       # 4,1 Coding Scheme Designator
    (0008,0104) LO [Retain Longitudinal Temporal Information Modified Dates Option]  # 62,1 Code Meaning
  (fffe,e00d)
  (fffe,e000) na (Item with undefined length)
    (0008,0100) SH [113111]                                     # 6,1 Code Value
    (0008,0102) SH [DCM ]                                       # 4,1 Coding Scheme Designator
    (0008,0104) LO [Retain Safe Private Option]                 # 26,1 Code Meaning
  (fffe,e00d)
(fffe,e0dd)
```

## License

The images are open source and were provided by [Rob Reid](https://github.com/captainnova) (@captainnova) and [Christopher G. Schwarz](https://github.com/CGSchwarzMayo) (@CGSchwarzMayo). This data is covered by the [2-clause BSD license](https://opensource.org/licenses/BSD-2-Clause).

## Running

Assuming that the executable dcm2niix is in your path, you should be able to simply run the script `batch.sh` from the terminal.

