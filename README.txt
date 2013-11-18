Concept:
The delay time is set by an envelope follower that measures the time between attacks and sets the delay to that time or a multiplier of it.  

Use a signal with clear attacks for the trigger.  Drums and clean guitar work well.  If you want a fuzzy guitar, run the clean signal to the trigger and the processed signal to the audio ins.  The trigger does not need to be the same instrument as the audio, so for example, drums can control the delay times on a pad.  

revision history
0.7.2
* reconfigure delay calculator to provide more stable delay lengths
* insert envelope after delay line to remove clicks
* inertia is set to 0 when auto inertia turned off
delay feedback set to exponential curve ( x^.5)
0.7.1 2/22/10
* put num/den contols into main menu
* added new numerator presets 15 and 17
0.7
* put right and left delay controls into main menu
0.6
* groupified the guts
* made it stereo with cross feedback
* added control to bypass inertia...helps with clicks
* UI reorg
* general dusting and cleaning
* Bypass smoother (inertia) if set to 1 ms in order to reduce clicking sounds

0.5
* Put sanitizers in signal path to prevent denormal problems
* put (RhythmEcho) after cc to param to avoid confusion in midi learn

0.4
* separate trigger signal from sample input
* set output of logic gates to PrevX(1) Fx and fed back into gates as false value prevent output of zeros to keep delay times in bounds.
* added autosmooth function so that smoothing (inertia) time matches (or if over 1 sec, is half of) delay time, making smoothing relate to the timing of the music too.
* added monitoring of delay time in ms to gui
*adjusted min and max of gui volumes so that max=1
* changed '<' back to '>' on envelope matching
* added midi cc to params and midi input so that midi mappings stay put for m-Audio Radium61 keyboard.
* took out spectral processing
0.3
* improved wet/dry mix
* moved multiplier from accum input to after minimum time but before maximum time.  This allows for very short delays without _unwanted_ combing and keeps preventing delays longer than the delay can handle.  
*changed denominator of multiplier from 32 to 64 to allow shorter delays. 
0.2
* changed direction of first binary op from "<" to ">".
* added min (4410 samples) and max (65535 samples) delay times to get rid of combing effects.
* changed accum factor from single number to two integer sliders to give fractions from 12/1 to 1/32
* changed mixing from wet/dry signal to single in single out with balance.
* added spectral freq and magnitude gates before envelope to increase sensitivity of beat detection.  
* re-mapped midi parameters  
0.1
*The beat sensing is not so great right now.  It needs to 1)reject times uner 50 milliseconds and 2) pick up the transients better.
* added feedback loop and limiter to circuit
* added smoother, which slows down the change in the delay times, creating a swooping effect when set above 1.
* Changed first greater than back to less than: if delayed (i.e., older) time times slope ratio is _less than_ undelayed  (present) time there has been a jump in volume. 
