# HD-tDCS Mind-Wandering EEG — Preprocessing Pipeline

## Pipeline: A1: 0.5-40Hz, ASR(BurstRej=ON, ChanCrit=OFF, LineNoise=4, Burst=20)

### Steps
1. Import .easy (Enobio32 / Neuroelectrics)
2. Remove auxiliary channels (X, Y, Z accelerometers)
3. Assign Enobio32 channel locations (Neuroelectrics plugin)
4. Bandpass filter (pop_eegfiltnew)
5. Artifact Subspace Reconstruction (pop_clean_rawdata)
   - ChannelCriterion: OFF
   - LineNoiseCriterion: 4
   - BurstCriterion: 20
   - BurstRejection: ON
6. Average reference
7. ICA (extended runica, maxsteps=300)
8. ICLabel artifact rejection (Eye>=0.90, Muscle>=0.90)
9. Spherical interpolation of removed channels
10. Epoch: Marker 7 (PROBE_Q1_START), [-4000 +1000] ms

### Software
- MATLAB R2026a
- EEGLAB (with Neuroelectrics 1.8, bids-matlab-tools 8.0, ICLabel)

### Key marker
- Marker 7 = PROBE_Q1_START (pre-probe epochs anchored here)
- TASK_END = 99
