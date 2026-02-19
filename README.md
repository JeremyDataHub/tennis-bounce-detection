# Tennis Ball Bounce Detection & Tactical Zone Visualization

Multi-camera computer vision system for automatic tennis ball bounce detection and tactical zone visualization designed for amateur training structures as an **affordable alternative** to professional systems like Hawk-Eye, Playsight or even SwingVision.

## 📽️ Demo


## ⚙️ System Pipeline

```
Camera 1 (4K 60fps)  ──┐
                        ├──▶ Synchronization ──▶ Intrinsic Calibration
Camera 2 (4K 60fps)  ──┘                              │
                                                       ▼
                                            Extrinsic Calibration
                                            (12 court reference points)
                                                       │
                                                       ▼
                                         3D Court Reconstruction
                                         (Midpoint triangulation +
                                          Levenberg-Marquardt)
                                                       │
                                                       ▼
                                    Ball Tracking (GridTrackNet)
                                    2D coordinates → 3D triangulation
                                                       │
                                                       ▼
                                      Bounce Detection
                                      (Local minima of Z-trajectory)
                                                       │
                                                       ▼
                              Tactical Zone Visualization
                              (Side-by-side video: acquisition + top-down view)
