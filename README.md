  <p align="center">
  <img width="200" height="200" src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/Mark-Zones-Icon.png?raw=true">
  </p>

  # Mark Zones

  This is a plugin for Glyphs 3.

  💡 Minimum Glyphs version: build <code>3062</code>.

  ⚠️ Do not download directly from here. Please install via GlyphsApp’s Plugin Manager ⚠️

  ## What does it do?

  Display Zones per master, per script in different colors.
  Optionally with a name and overshoot, or dashed if it’s just a line.

  ### Types of Zones
  
  - Zones as *pair*
  
  - Zones as *guide line*
  
  Either type of zone can have an overshoot  
  
  - Pairs’ overshoots go into both directions away from the zone.
  
  - Lines’ overshoots go up for y-positions higher than 0 and downwards otherwise.

  ## How to use

  ### To create a zone, you have to options:
  a) Create it from scratch:
  - In `Font Info` > `Masters` add a new Custom Parameter for each desired master, called *`MarkZones`*
  
  b) From a selection:
  - You can select a path or some nodes and use the context menu (right click into the Edit View) > `Make Mark Zone`, which will create a zone from the selection’s vertical dimensions.
  
  Then you can adjust the created zone in the user interface by clicking on the custom parameter.

  ## NOTES:
  - It is best to hide the GlyphsApp metrics (`⌘+⇧+M`), because this plugin draws its own metrics
  - If a Zone is called _"Anchors"_, all anchors that are _not_ on one of those zones will be highlighted
  - Nodes on zones will be highlighted if they are on a zone’s overshoot or exactly on the border of a zone.
  - You can toggle display of a zone via the checkbox for the Custom Parameter, if you want to keep but hide it

  &nbsp;
  ## Highlights

  - You can now download it directly from the Plugin Manager right inside of GlyphsApp.

  &nbsp;
  ## Todo

  - See [issues](https://github.com/Mark2Mark/mark-zones-plugin/issues)

  ## Bugs

  - Currently Italic angle is not supported

  &nbsp;
  ## Changelog

  <details><summary>Expand if you’re curious.</summary>

  ### v1.0.0

  - New in GlyphsApp's Plugin Manager
  - Custom Parameter now as a UI, so you don’t have to write it manually

  </details>

  &nbsp;
  ## FAQ
  <details><summary>🙋 I can’t find it in the Plugin Manager.</summary>
  ➡️ You need to check if your GlyphsApp build is higher than <code>3062</code>.  
  If Glyphs doesn’t offer you a high enough version, enable activate GlyphsApp <code>Preferences</code> > <code>"Updates"</code> > <code>“Show cutting edge versions”</code>. Note: you can have several GlyphsApp versions
  </details>

  &nbsp;
  ## How to activate your license<a id="how-to-activate-your-license"></a>  
  After your purchase, the license key should be set automatically for you. If it isn’t:  
  <details><summary>Activating the plugin is easy, just follow the simple steps [click to open]</summary>
  <ol>
    <li>👉 Make sure you have GlyphsApp 3 build <code>3062</code> or higher.</li>
    <li>👉 If you haven't already, download the plugin directly in the GlyphsApp Plugin Manager and restart GlyphsApp once.</li>
    <li>👉 When you activate the plugin, you'll be prompted with a window*, click the <code>"Enter License"</code> button.</li>
    <li>👉 On the screen that opens enter your Email address, and the license code from your Email.</li>
    <li>👉 When you've completed the above, just click the <code>"Activate License"</code> button. Within a few seconds your product should be activated for full use!</li>
  </ol>

  *) If the window doesn’t show, you can right-click into the Edit Tab (that’s the window where you do your drawings) and in the context menu click <code>"Purchase Mark Zones"</code>. Alternatively you can right click into the plugin’s Preview box and click <code>"Open Registration Window"</code>.
  </details>

  &nbsp;
  ## How to enter a coupon
  <details><summary>If you have a coupon, follow these steps to use it for a discount on your purchase [click to open]</summary>
  <ol>
    <li>👉 Make sure you have GlyphsApp 3 build <code>3062</code> or higher.</li>
    <li>👉 If you haven't already, download the plugin directly in the GlyphsApp Plugin Manager and restart GlyphsApp once.</li>
    <li>👉 When you activate the plugin, you'll be prompted with a window*, click the <code>"Buy Now"</code> button.</li>
    <li>👉 On the screen that opens enter your Email address, and click <code>»Continue«</code>.</li>
    <li>👉 Follow the form until it asks you to pay. But now click <code>»Add Coupon«</code> and then continue to pay.</li>
    <li>👉 On success you should get an Email with a licence code.</li>
    <li>👉 Use that to activate your license <a href="#how-to-activate-your-license"> (steps here).</a> </li>
  </ol>

  ⚠️ Note: The Coupon is **not** the License Code. Please don’t enter the Coupon Code into the field for your License Code!

  *) If the window doesn’t show, you can right-click into the Edit Tab (that’s the window where you do your drawings) and in the context menu click <code>"Purchase Mark Zones"</code>. Alternatively you can right click into the plugin’s Preview box and click <code>"Open Registration Window"</code>.

  If you can’t see the <code>»Add Coupon«</code>, that’s likely to a reported GlyphsApp bug, switching to Dark Mode and opening the window again might solve it.
</details>

&nbsp;

---

<p align="center">
  <img src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/Mark%20Zones.png?raw=true">
  Ecample with some zones active
</p>

<p align="center">
  <img width="300" src="https://github.com/Mark2Mark/mark-zones-plugin/blob/main/.images/Mark%20Zones%20UI.png?raw=true">
  User Interface for the Custom Parameter
</p>