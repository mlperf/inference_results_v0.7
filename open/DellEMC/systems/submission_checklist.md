# MLPerf Inference 0.5 Self-Certification Checklist

Name of Certifying Engineer(s): Aaron Ng, Bryan Lozano, Sam Sun, Rex Wang, Yue Gao, Bader Alam, Sumit Nagpal, Mahesh Mahadurkar, Bhavesh Patel

Email of Certifying Engineer(s): {aaronn, bryanloz, xsun, rexwang, gaoyue, badermd, sumitn, maheshm}@xilinx.com, bhavesh.a.patel@dell.com

Name of System(s) Under Test: dpuv3me dpuv4e

Division:
- [X] Open
- [ ] Closed

Category:
- [X] Available
- [ ] Preview
- [X] Research, Development, and Internal (RDI)

Benchmark:
- [ ] MobileNet
- [X] SSD-MobileNet
- [X] ResNet
- [ ] SSD-1200
- [ ] NMT
- [ ] Other, please specify:

Please fill in the following tables adding lines as necessary:
97%-tile latency is required for NMT only. 99%-tile is required for all other models.

### Single Stream Results Table
| SUT Name | Benchmark | Query Count | Accuracy |
|----------|-----------|-------------|----------|
|  v3me    | SSD-MobileNet | 1024   |          |

### Server Results Table
| SUT Name | Benchmark | Query Count | Accuracy | 97%-tile Latency | 99%-tile Latency |
|----------|-----------|-------------|----------|------------------|------------------|
|  v4e     | ResNet    |  >= 270336   |          |                  |                  |


### Offline Results Table
| SUT Name | Benchmark | Sample Count | Accuracy | 
|----------|-----------|--------------|----------|
|  v4e     | ResNet        | > 24576        |          |
|  v3me    | SSD-MobileNet | > 24576        |          |

Scenario (check all that apply):
- [X] Single-Stream
- [ ] Multi-Stream
- [X] Server
- [X] Offline

For each SUT, does the submission meet the latency target for each
combination of benchmark and scenario? (check all that apply)
- [X] Yes (Single-Stream and Offline no requirements)
- [ ] Yes (MobileNet x Multi-Stream 50 ms @ 99%)
- [ ] Yes (MobileNet x Server 10 ms @ 99%)
- [ ] Yes (SSD-MobileNet x Multi-Stream 50 ms @ 99%)
- [ ] Yes (SSD-MobileNet x Server 10 ms @ 99%)
- [ ] Yes (ResNet x Multi-Stream 50 ms @ 99%)
- [X] Yes (ResNet x Server 15 ms @ 99%)
- [ ] Yes (SSD-1200 x Multi-Stream 66 ms @ 99%).
- [ ] Yes (SSD-1200 x Server 100 ms @ 99%)
- [ ] Yes (NMT x Multi-Stream 100 ms @ 97%)
- [ ] Yes (NMT x Server 250 ms @ 97%)
- [ ] No

For each SUT, is the appropriate minimum number of queries or samples
met, depending on the Scenario x Benchmark? (check all that apply)
- [X] Yes (Single-Stream 1,024 queries)
- [X] Yes (Offline 24,576 samples)
- [ ] Yes (NMT Server and Multi-Stream 90,112 queries)
- [X] Yes (Image Models Server and Multi-Stream 270,336 queries)
- [ ] No

For each SUT and scenario, is the benchmark accuracy target met?
(check all that apply)
- [ ] Yes (MobileNet 71.68% x 98%)
- [X] Yes (SSD-MobileNet 0.22 mAP x 99%)
- [X] Yes (ResNet 76.46% x 99%)
- [ ] Yes (SSD-1200 0.20 mAP x 99%)
- [ ] Yes (NMT 23.9 BLEU x 99%)
- [ ] No


For each SUT and scenario, did the submission run on the whole
validation set in accuracy mode? (check one)
- [X] Yes
- [ ] No

How many samples are loaded into the QSL in performance mode?

For each SUT and scenario, does the number of loaded samples in the
QSL in performance mode meet the minimum requirement?  (check all that
apply)
- [X] Yes (ResNet and MobileNet 1,024 samples)
- [X] Yes (SSD-MobileNet 256 samples)
- [ ] Yes (SSD-1200 64 samples)
- [ ] Yes (NMT 3,903,900 samples)
- [ ] No

For each SUT and scenario, is the experimental duration greater than
or equal to 60 seconds?  (check one)
- [X] Yes
- [ ] No

Does the submission use LoadGen? (check one)
- [X] Yes
- [ ] No

Is your loadgen commit from one of these allowed commit hashes?
- [ ] 61220457dec221ed1984c62bd9d382698bd71bc6
- [ ] 5684c11e3987b614aae830390fa0e92f56b7e800
- [ ] 55c0ea4e772634107f3e67a6d0da61e6a2ca390d
- [ ] d31c18fbd9854a4f1c489ca1bc4cd818e48f2bc5
- [ ] 1d0e06e54a7d763cf228bdfd8b1e987976e4222f
- [X] Other, please specify: af9a931721f580d47a8265006b8019ed56da6fd3

Do you have any additional change to Loadgen? (check one)
- [ ] Yes, please specify:
- [X] No

Does the submission run the same code in accuracy and performance
modes? (check one)
- [X] Yes
- [ ] No

Where is the LoadGen trace stored? (check one)
- [X] Host DRAM
- [ ] Other, please specify:

For the submitted result, what is the QSL random number generator seed?
- [X] 12786827339337101903
- [ ] Other, please specify:

For the submitted results, what is the sample index random number generator seed?
- [X] 12640797754436136668
- [ ] Other, please specify:

For the submitted results, what is the schedule random number generator seed?
- [X] 3135815929913719677
- [ ] Other, please specify:

For each SUT and scenario, is the submission run the correct number of
times for the relevant scenario? (check one)
- [X] Yes (Accuracy 1x Performance 1x Single-Stream, Multi-Stream,
Offline)
- [X] Yes (Accuracy 1x Performance 5x Server)
- [ ] No

Are the weights calibrated using data outside of the calibration set?
(check one)
- [ ] Yes
- [X] No

What untimed pre-processing does the submission use? (check all that apply)
- [X] Resize
- [X] Reorder channels or transpose
- [ ] Pad
- [ ] A single crop
- [X] Mean subtraction and normalization
- [X] Convert to whitelisted format
- [ ] No pre-processing
- [ ] Other, please specify:

What numerics does the submission use? (check all that apply)
- [ ] INT4
- [X] INT8
- [ ] INT16
- [ ] UINT8
- [ ] UINT16
- [ ] FP11
- [ ] FP16
- [ ] BF16
- [ ] FP32
- [ ] Other, please specify:

Which of the following techniques does the submission use? (check all
that apply)
- [ ] Wholesale weight replacement
- [ ] Weight supplements
- [ ] Discarding non-zero weight elements
- [X] Pruning
- [ ] Caching queries
- [ ] Caching responses
- [ ] Caching intermediate computations
- [ ] Modifying weights during the timed portion of an inference run
- [ ] Weight quantization algorithms that are similar in size to the
non-zero weights they produce
- [ ] Hard coding the total number of queries
- [ ] Techniques that boost performance for fixed length experiments but
are inapplicable to long-running services except in the offline
scenario
- [ ] Using knowledge of the LoadGen implementation to predict upcoming
lulls or spikes in the server scenario
- [ ] Treating beams in a beam search differently. For example,
employing different precision for different beams
- [ ] Changing the number of beams per beam search relative to the reference
- [ ] Incorporating explicit statistical information about the performance or accuracy sets
- [ ] Techniques that take advantage of upsampled images.
- [ ] Techniques that only improve performance when there are identical samples in a query.
- [X] None of the above

Is the submission congruent with all relevant MLPerf rules?
- [X] Yes
- [ ] No

For each SUT, does the submission accurately reflect the real-world
performance of the SUT?
- [X] Yes
- [ ] No
