# datasettype_transfer_lists
Repo to hold YAML-formatted lists of `dataset_type` entries for `rucio-register auto-register` to parse and filter on.

Each list should contain all possible `dataset_type` names. Dataset types commented out will not be registered by `rucio-register auto-register`, therefore, dataset types for which transfer from remote DFs to USDF it _not_ required should be commented out with '`#`' and a reason given, e.g., "`# - analyzeInitialSummaryStats_config  # (config/log/metadata)`".

The YAML format is `<stage>.<step>.dataset_type`. For example, [cm_transfer_list.yaml](cm_transfer_list.yaml), snippet below.

```yaml
stage1:
  step1a:
    # - analyzeAmpInterfaceOffsetMetadata_config  # (config/log/metadata)
    # - analyzeAmpInterfaceOffsetMetadata_log  # (config/log/metadata)
    # - analyzeAmpInterfaceOffsetMetadata_metadata  # (config/log/metadata)
    # - analyzeAmpOffsetMetadata_config  # (config/log/metadata)
    # - analyzeAmpOffsetMetadata_log  # (config/log/metadata)
    # - analyzeAmpOffsetMetadata_metadata  # (config/log/metadata)
    # - analyzeCalibrateImageMetadata_config  # (config/log/metadata)
    # - analyzeCalibrateImageMetadata_log  # (config/log/metadata)
    # - analyzeCalibrateImageMetadata_metadata  # (config/log/metadata)
    # - analyzeInitialSummaryStats_config  # (config/log/metadata)
    # - analyzeInitialSummaryStats_log  # (config/log/metadata)
    # - analyzeInitialSummaryStats_metadata  # (config/log/metadata)
    - background_to_photometric_ratio
    # - calibrateImage_config  # (config/log/metadata)
    # - calibrateImage_log  # (config/log/metadata)
    # - calibrateImage_metadata  # (config/log/metadata)
    # - initial_astrometry_match_detector  # (intermediate catalog/metadata)
    # - initial_photoCalib_detector  # (intermediate catalog/metadata)
    # - initial_photometry_match_detector  # (intermediate catalog/metadata)
    - isrStatistics
    # - isr_config  # (config/log/metadata)
    # - isr_log  # (config/log/metadata)
    # - isr_metadata  # (config/log/metadata)
    - isr_metrics
    # - packages  # (environment package info)
    # - postIsrBin1  # (default non-transfer)
    # - postIsrBin2  # (default non-transfer)
    # - post_isr_image  # (intermediate image/warp/catalog)
    # - preInterpISRCCD  # (default non-transfer)
    # - preliminary_visit_image  # (intermediate image/warp/catalog)
    # - preliminary_visit_image_background  # (intermediate image/warp/catalog)
    # - preliminary_visit_mask  # (intermediate image/warp/catalog)
    # - single_visit_psf_star  # (default non-transfer)
    # - single_visit_psf_star_footprints  # (intermediate catalog/metadata)
    # - single_visit_star_detector  # (intermediate catalog/metadata)
    # - single_visit_star_footprints  # (intermediate catalog/metadata)
    # - single_visit_star_schema  # (intermediate catalog/metadata)
    # - single_visit_star_unstandardized  # (intermediate catalog/metadata)
    # - standardizeSingleVisitStar_config  # (config/log/metadata)
    # - standardizeSingleVisitStar_log  # (config/log/metadata)
    # - standardizeSingleVisitStar_metadata  # (config/log/metadata)
```

> Note: new dataset types are added all the time - this repo does not currently solve the problem of dataset-type transfer lists becoming outdated. One solution may be to have a master list that is kept up to date (either manually or via CI) and a CI job to add any new dataset types to other lists as new, uncommented, entries for manual curation.
