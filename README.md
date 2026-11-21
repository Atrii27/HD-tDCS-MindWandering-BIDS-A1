# HD-tDCS Mind-Wandering EEG (BIDS A1)

Pipeline: 0.5–40 Hz  |  ASR: BurstRejection=ON, ChannelCriterion=OFF, LineNoise=4, Burst=20

Steps: .easy import → aux removal → Enobio32 locs → bandpass → ASR → avg ref → ICA → ICLabel → interpolation → Marker-7 epoch [-4 +1 s]

Software: MATLAB R2026a, EEGLAB (Neuroelectrics 1.8, ICLabel)
Key marker: 7 = PROBE_Q1_START, 99 = TASK_END
