Speedflip Speed Calculator
==========================

A single-page web tool that calculates the Speed= value for the air roll
keybind in Rocket League's TAInput.ini, so you can hit a chosen speedflip
diagonal angle on keyboard.

Usage
-----
1. Open index.html in any modern browser. No install or build step.
   To host it on GitHub Pages, keep the file name as index.html.
2. Enter the flip angle (0.1 to 45 degrees) and the framerate the game
   will be locked at.
3. Pick the bind side: Right (E) or Left (Q).
4. Copy the generated PCBindings line into TAInput.ini.

The Advanced section holds the scale constant K. Leave it at 100 unless
you are recalibrating from your own measurements.

How it works
------------
    r     = tan(angle)
    Speed = r * fps / K        (K = 100 by default)

Roll input is snapped to the nearest step of the signed byte axis
(128 steps left, 127 steps right), and the page shows the resulting
angle. Deadzone is treated as 0.00 because it has no observed effect on
these values.

Limitations
-----------
- Assumes W has no Speed= of its own, so it stays at full pitch.
- Assumes a steady framerate. A fluctuating fps changes the angle.
- Angles below about 11.5 degrees probably give a straight dodge instead
  of a diagonal, whatever the Speed value.
- K was fitted from one measurement, so results may differ on your setup.

Credit
------
The speedflip Speed= method builds on a post by u/ignice on Reddit.

License
-------
No rights reserved. Copy, modify and share freely.
