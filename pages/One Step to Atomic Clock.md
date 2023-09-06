- If you are one of those people who find it easy to build a radio and feasible to build a phase-locked loop (and also know a bit of optics), you can do it. Here is an abbreviated recipe for a simple atomic clock. You’ll need
- A rubidium discharge lamp, inside a magnetic shield
- A photodetector
- A 6.83 GHz voltage controlled oscillator, ideally a DRO (purist: build it yourself)
- A frequency divider
- A local oscillator LO at a few 100 kHz
- A synchronous detector,
- A servo amplifier (could be a simple op-amp)
  
  The rubidium lamp shines onto the detector, whose output signal is amplified. The DRO shines microwaves onto the lamp.
  
  The idea is that the light output of the lamp drops by a fraction of a per-cent when the DRO frequency hits the Rb ground state hyperfine transition at 6,834,682,610.904 Hz.
  
  To keep the DRO frequency at that value, the DRO is frequency modulated by the LO. This will in general cause a modulation of the light output of the lamp at the LO frequency, unless the DRO is tuned exactly to the hyperfine transition frequency.
  
  The synchronous detector (such as some Analog Devices chip) detects that modulation, and the servo amplifier controls the frequency of the DRO to stay on resonance. If everything works fine, your DRO will now be maintained at 6,834,682,610.904 Hz (save for systematic errors, caused., e.g., by stray magnetic fields; hence the shielding).
  
  The frequency divider is now set to count the oscillations of the DRO and produce one output pulse per 6,834,682,611 cycles of the DRO. Voila, a clock ticking once per second.
  
  For better performance, phase-lock the DRO to a high-quality crystal oscillator reference. Also, rounding 6,834,682,610.904≈6,834,682,6116,834,682,610.904≈6,834,682,611 simplifies construction, but reduces the accuracy of the clock; you could use a DDS frequency synthesizer to avoid rounding.
  
  The rubidium lamp will be the hardest to come by, though I guess it doesn’t need to be expensive. A commercial DRO will cost hundreds of bucks new, but you could try to find a used one or build it yourself (this will require a lot of specialized knowledge in its own right).