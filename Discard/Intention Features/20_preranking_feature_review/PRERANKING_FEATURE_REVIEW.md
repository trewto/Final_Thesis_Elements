# Pre-ranking feature and redundancy review

## Status

Training data only. Ranking, validation and final test have not been run in this revised pathway. User decisions are required before ranking.

## Variable-type correction

Traffic counts are now processed as numerical count variables. `waiting_low_speed_time_sec` is reported as `low_velocity_total_waiting_time_sec` and retained only for later sensitivity analysis outside the fixed two-second-history primary set.

## Summary

### individual

- training_rows: 28139
- candidate_rows: 77
- numeric_or_count: 64
- categorical_or_binary: 13
- numeric_pairs_ge_0p80: 51
- numeric_pairs_ge_0p90: 14
- categorical_pairs_v_ge_0p80: 3
- sparse_rxk_horizon_tables: 9
- raw_vif_ge_5: 37

### group_snapshot

- training_rows: 3691
- candidate_rows: 91
- numeric_or_count: 80
- categorical_or_binary: 11
- numeric_pairs_ge_0p80: 92
- numeric_pairs_ge_0p90: 31
- categorical_pairs_v_ge_0p80: 3
- sparse_rxk_horizon_tables: 9
- raw_vif_ge_5: 57

## Highest numerical redundancy pairs

| dataset | feature_1 | feature_2 | spearman_rho | screening_zone |
|---|---|---|---|---|
| individual | history_observed_fraction | history_max_unobserved_gap_sec | -0.9958 | hard_same_concept_review_ge_0p90 |
| individual | history_mean_vx_mps | history_x_displacement_m | 0.9946 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_companion_low_speed_wait_mean_sec | dbscan_companion_low_speed_wait_max_sec | 0.9938 | hard_same_concept_review_ge_0p90 |
| individual | history_mean_vy_mps | history_y_displacement_m | 0.991 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_companion_wait_mean_sec | dbscan_companion_wait_max_sec | 0.987 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_history_mean_group_size | dbscan_history_mean_spread_m | 0.9773 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_companion_wait_max_sec | dbscan_companion_low_speed_wait_max_sec | 0.9511 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_companion_wait_max_sec | dbscan_companion_low_speed_wait_mean_sec | 0.9444 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_companion_wait_mean_sec | dbscan_companion_low_speed_wait_mean_sec | 0.9438 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_companion_wait_mean_sec | dbscan_companion_low_speed_wait_max_sec | 0.9344 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_companion_low_speed_fraction | dbscan_companion_low_speed_wait_mean_sec | 0.9331 | hard_same_concept_review_ge_0p90 |
| individual | veh3_speed_mps | veh3_closing_speed_mps | 0.925 | hard_same_concept_review_ge_0p90 |
| individual | history_mean_speed_mps | dbscan_history_mean_speed_mps | 0.914 | hard_same_concept_review_ge_0p90 |
| individual | dbscan_companion_low_speed_fraction | dbscan_companion_low_speed_wait_max_sec | 0.907 | hard_same_concept_review_ge_0p90 |
| individual | waiting_band_dwell_sec | waiting_low_speed_time_sec | 0.8958 | manual_review_0p80_to_0p90 |
| individual | veh2_speed_mps | veh2_closing_speed_mps | 0.8951 | manual_review_0p80_to_0p90 |
| individual | dbscan_companion_wait_mean_sec | dbscan_companion_low_speed_fraction | 0.8882 | manual_review_0p80_to_0p90 |
| individual | veh2_front_y_m | veh2_history_mean_front_y_m | 0.887 | manual_review_0p80_to_0p90 |
| individual | history_mean_speed_mps | window_low_speed_fraction | -0.8851 | manual_review_0p80_to_0p90 |
| individual | veh1_front_y_m | veh1_history_mean_front_y_m | 0.8832 | manual_review_0p80_to_0p90 |
| individual | veh3_closing_speed_mps | veh3_history_front_y_change_m | -0.8817 | manual_review_0p80_to_0p90 |
| individual | history_mean_speed_mps | history_speed_std_mps | 0.8761 | manual_review_0p80_to_0p90 |
| individual | history_observed_fraction | history_interpolated_fraction | -0.8728 | manual_review_0p80_to_0p90 |
| individual | veh3_front_y_m | veh3_history_mean_front_y_m | 0.8706 | manual_review_0p80_to_0p90 |
| individual | veh3_speed_mps | veh3_history_front_y_change_m | -0.8687 | manual_review_0p80_to_0p90 |

## Highest categorical redundancy pairs

| dataset | feature_1 | feature_2 | cramers_v | screening_zone |
|---|---|---|---|---|
| individual | veh3_present | veh3_class | 0.9998 | manual_review_ge_0p80 |
| individual | veh2_present | veh2_class | 0.9998 | manual_review_ge_0p80 |
| individual | veh1_present | veh1_class | 0.9998 | manual_review_ge_0p80 |
| individual | veh3_present | veh2_class | 0.7877 | below_0p80 |
| individual | veh2_present | veh3_present | 0.7743 | below_0p80 |
| individual | veh2_present | veh3_class | 0.774 | below_0p80 |
| individual | veh2_present | veh1_class | 0.6835 | below_0p80 |
| individual | veh1_present | veh2_present | 0.6633 | below_0p80 |
| individual | veh1_present | veh2_class | 0.6629 | below_0p80 |
| individual | veh1_ttc_infinite | veh2_ttc_infinite | 0.6389 | below_0p80 |
| individual | veh2_ttc_infinite | veh3_ttc_infinite | 0.6103 | below_0p80 |
| individual | veh3_class | traffic_period | 0.5567 | below_0p80 |
| individual | veh3_present | veh1_class | 0.556 | below_0p80 |
| individual | veh1_present | veh3_present | 0.5135 | below_0p80 |
| individual | veh1_present | veh3_class | 0.5132 | below_0p80 |
| individual | veh2_class | traffic_period | 0.4652 | below_0p80 |
| individual | veh3_ttc_infinite | veh3_class | 0.444 | below_0p80 |
| individual | veh3_present | traffic_period | 0.4085 | below_0p80 |
| individual | veh1_ttc_infinite | veh3_ttc_infinite | 0.408 | below_0p80 |
| individual | veh3_present | veh3_ttc_infinite | 0.3981 | below_0p80 |

## Required user review

Complete `user_decision` and `user_note` in `ALL_FEATURE_DECISIONS_FOR_USER_REVIEW.csv`. No feature is automatically removed by this stage.