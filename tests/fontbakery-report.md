## Fontbakery report

Fontbakery version: 0.8.2

<details>
<summary><b>[3] Family checks</b></summary>
<details>
<summary>🔥 <b>FAIL:</b> Checking all files are in the same directory.</summary>

* [com.google.fonts/check/family/single_directory](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/family/single_directory)
<pre>--- Rationale ---
If the set of font files passed in the command line is not all in the same
directory, then we warn the user since the tool will interpret the set of files
as belonging to a single family (and it is unlikely that the user would store
the files from a single family spreaded in several separate directories).</pre>

* 🔥 **FAIL** Not all fonts passed in the command line are in the same directory. This may lead to bad results as the tool will interpret all font files as belonging to a single font family. The detected directories are: ['fonts/ttf', 'fonts/otf', 'fonts/variable'] [code: single-directory]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Check that OS/2.fsSelection bold & italic settings are unique for each NameID1</summary>

* [com.adobe.fonts/check/family/bold_italic_unique_for_nameid1](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/os2.html#com.adobe.fonts/check/family/bold_italic_unique_for_nameid1)
<pre>--- Rationale ---
Per the OpenType spec: name ID 1 &#x27;is used in combination with Font Subfamily
name (name ID 2), and should be shared among at most four fonts that differ only
in weight or style...
This four-way distinction should also be reflected in the OS/2.fsSelection
field, using bits 0 and 5.</pre>

* 🔥 **FAIL** Family 'Oswald' has 2 fonts (should be no more than 1) with the same OS/2.fsSelection bold & italic settings: Bold=True, Italic=False [code: unique-fsselection]
* 🔥 **FAIL** Family 'Oswald' has 2 fonts (should be no more than 1) with the same OS/2.fsSelection bold & italic settings: Bold=False, Italic=False [code: unique-fsselection]

</details>
<details>
<summary>🔥 <b>FAIL:</b> Verify that each group of fonts with the same nameID 1 has maximum of 4 fonts</summary>

* [com.adobe.fonts/check/family/max_4_fonts_per_family_name](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/name.html#com.adobe.fonts/check/family/max_4_fonts_per_family_name)
<pre>--- Rationale ---
Per the OpenType spec:
&#x27;The Font Family name [...] should be shared among at most four fonts that
differ only in weight or style [...]&#x27;</pre>

* 🔥 **FAIL** Family 'Oswald' has 5 fonts (should be 4 or fewer). [code: too-many]

</details>
<br>
</details>
<details>
<summary><b>[13] Oswald-Light.ttf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Font has old ttfautohint applied?</summary>

* [com.google.fonts/check/old_ttfautohint](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/old_ttfautohint)
<pre>--- Rationale ---
Check if font has been hinted with an outdated version of ttfautohint.</pre>

* ⚠ **WARN** ttfautohint used in font = 1.8.3; latest = 1.8.4; Need to re-run with the newer version! [code: old-ttfa]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [colonmonetary, lira, uni0462, uni046A, uni0493, uni20A6, uni20A9, uni20AD, uni20B1, uni20BA, uni2116]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---
Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will only
differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.
However, a quotedbl should have 2 contours, unless the font belongs to a display
family.
This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: uogonek	Contours detected: 2	Expected: 1
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni01EA	Contours detected: 3	Expected: 2
Glyph name: uni01EB	Contours detected: 3	Expected: 2
Glyph name: uni01F5	Contours detected: 4	Expected: 3
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: uni20B5	Contours detected: 3	Expected: 1 or 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: fi	Contours detected: 2	Expected: 3
Glyph name: fl	Contours detected: 1	Expected: 2
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: uni20B5	Contours detected: 3	Expected: 1 or 2
Glyph name: uogonek	Contours detected: 2	Expected: 1 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* asterisk (U+002A): X=166.0,Y=809.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=223.0,Y=809.0 (should be at cap-height 810?)
	* at (U+0040): X=464.0,Y=809.0 (should be at cap-height 810?)
	* m (U+006D): X=541.5,Y=576.0 (should be at x-height 578?)
	* t (U+0074): X=255.0,Y=-1.0 (should be at baseline 0?)
	* braceleft (U+007B): X=158.5,Y=810.5 (should be at cap-height 810?)
	* braceright (U+007D): X=110.5,Y=810.5 (should be at cap-height 810?)
	* questiondown (U+00BF): X=131.0,Y=1.0 (should be at baseline 0?)
	* uni0163 (U+0163): X=255.0,Y=-1.0 (should be at baseline 0?)
	* tcaron (U+0165): X=255.0,Y=-1.0 (should be at baseline 0?) and 48 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* uni040E (U+040E): L<<102.0,810.0>--<185.0,447.0>> -> L<<185.0,447.0>--<239.0,186.0>>
	* uni040E (U+040E): L<<239.0,186.0>--<286.0,447.0>> -> L<<286.0,447.0>--<360.0,810.0>>
	* uni0423 (U+0423): L<<102.0,810.0>--<185.0,447.0>> -> L<<185.0,447.0>--<239.0,186.0>>
	* uni0423 (U+0423): L<<239.0,186.0>--<286.0,447.0>> -> L<<286.0,447.0>--<360.0,810.0>>
	* uni04EE (U+04EE): L<<102.0,810.0>--<185.0,447.0>> -> L<<185.0,447.0>--<239.0,186.0>>
	* uni04EE (U+04EE): L<<239.0,186.0>--<286.0,447.0>> -> L<<286.0,447.0>--<360.0,810.0>>
	* uni04F0 (U+04F0): L<<102.0,810.0>--<185.0,447.0>> -> L<<185.0,447.0>--<239.0,186.0>>
	* uni04F0 (U+04F0): L<<239.0,186.0>--<286.0,447.0>> -> L<<286.0,447.0>--<360.0,810.0>>
	* uni04F2 (U+04F2): L<<102.0,810.0>--<185.0,447.0>> -> L<<185.0,447.0>--<239.0,186.0>> and uni04F2 (U+04F2): L<<239.0,186.0>--<286.0,447.0>> -> L<<286.0,447.0>--<360.0,810.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * onequarter (U+00BC): L<<606.0,168.0>--<605.0,342.0>>
 * threequarters (U+00BE): L<<669.0,168.0>--<668.0,342.0>>
 * uni00B5 (U+00B5): L<<52.0,-173.0>--<51.0,578.0>>
 * uni043C (U+043C): L<<116.0,404.0>--<115.0,0.0>>
 * uni043C (U+043C): L<<381.0,0.0>--<380.0,406.0>>
 * uni043C (U+043C): L<<439.0,578.0>--<444.0,0.0>>
 * uni043C (U+043C): L<<52.0,0.0>--<57.0,578.0>>
 * uni04CE (U+04CE): L<<116.0,404.0>--<115.0,0.0>>
 * uni04CE (U+04CE): L<<381.0,0.0>--<380.0,406.0>>
 * uni04CE (U+04CE): L<<439.0,578.0>--<443.0,52.0>>
 * uni04CE (U+04CE): L<<52.0,0.0>--<57.0,578.0>> and uni2074 (U+2074): L<<220.0,601.0>--<219.0,775.0>> [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[14] Oswald-Bold.ttf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Font has old ttfautohint applied?</summary>

* [com.google.fonts/check/old_ttfautohint](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/old_ttfautohint)
<pre>--- Rationale ---
Check if font has been hinted with an outdated version of ttfautohint.</pre>

* ⚠ **WARN** ttfautohint used in font = 1.8.3; latest = 1.8.4; Need to re-run with the newer version! [code: old-ttfa]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [Oslash, Oslashacute, Tbar, Ustraitstrokecy, colonmonetary, emptyset, franc, k, lira, oslash, oslashacute, tbar, uni0137, uni01E4, uni01E5, uni01E9, uni0426, uni0429, uni0452, uni045B, uni0462, uni0463, uni046A, uni046B, uni0492, uni0493, uni0497, uni049B, uni04CA, uni04E8, uni04E9, uni20A6, uni20A9, uni20AD, uni20B1, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, ustraitstrokecy]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---
Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will only
differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.
However, a quotedbl should have 2 contours, unless the font belongs to a display
family.
This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: uogonek	Contours detected: 2	Expected: 1
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni01EA	Contours detected: 3	Expected: 2
Glyph name: uni01EB	Contours detected: 3	Expected: 2
Glyph name: uni01F5	Contours detected: 4	Expected: 3
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: fi	Contours detected: 2	Expected: 3
Glyph name: fl	Contours detected: 1	Expected: 2
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: uogonek	Contours detected: 2	Expected: 1 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* exclam (U+0021): X=49.0,Y=808.0 (should be at cap-height 810?)
	* exclam (U+0021): X=211.0,Y=808.0 (should be at cap-height 810?)
	* percent (U+0025): X=234.0,Y=811.0 (should be at cap-height 810?)
	* percent (U+0025): X=770.0,Y=-1.0 (should be at baseline 0?)
	* percent (U+0025): X=770.0,Y=-1.0 (should be at baseline 0?)
	* J (U+004A): X=214.5,Y=1.5 (should be at baseline 0?)
	* W (U+0057): X=288.0,Y=809.0 (should be at cap-height 810?)
	* W (U+0057): X=407.0,Y=809.0 (should be at cap-height 810?)
	* m (U+006D): X=277.5,Y=576.0 (should be at x-height 578?)
	* t (U+0074): X=330.0,Y=2.0 (should be at baseline 0?) and 86 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* partialdiff (U+2202): L<<215.0,385.0>--<192.0,150.0>> -> L<<192.0,150.0>--<192.0,142.0>>
	* uni040E (U+040E): L<<188.0,810.0>--<258.0,477.0>> -> L<<258.0,477.0>--<291.0,260.0>>
	* uni040E (U+040E): L<<291.0,260.0>--<315.0,478.0>> -> L<<315.0,478.0>--<374.0,810.0>>
	* uni0423 (U+0423): L<<188.0,810.0>--<258.0,477.0>> -> L<<258.0,477.0>--<291.0,260.0>>
	* uni0423 (U+0423): L<<291.0,260.0>--<315.0,478.0>> -> L<<315.0,478.0>--<374.0,810.0>>
	* uni04EE (U+04EE): L<<188.0,810.0>--<258.0,477.0>> -> L<<258.0,477.0>--<291.0,260.0>>
	* uni04EE (U+04EE): L<<291.0,260.0>--<315.0,478.0>> -> L<<315.0,478.0>--<374.0,810.0>>
	* uni04F0 (U+04F0): L<<188.0,810.0>--<258.0,477.0>> -> L<<258.0,477.0>--<291.0,260.0>>
	* uni04F0 (U+04F0): L<<291.0,260.0>--<315.0,478.0>> -> L<<315.0,478.0>--<374.0,810.0>>
	* uni04F2 (U+04F2): L<<188.0,810.0>--<258.0,477.0>> -> L<<258.0,477.0>--<291.0,260.0>> and uni04F2 (U+04F2): L<<291.0,260.0>--<315.0,478.0>> -> L<<315.0,478.0>--<374.0,810.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---
This check heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed up
by manual inspection.</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* M (U+004D): L<<298.0,0.0>--<198.0,543.0>>/L<<198.0,543.0>--<186.0,0.0>> = 11.700788695776946
	* M (U+004D): L<<520.0,0.0>--<505.0,539.0>>/L<<505.0,539.0>--<411.0,0.0>> = 11.486811882048746
	* W (U+0057): L<<179.0,810.0>--<227.0,338.0>>/L<<227.0,338.0>--<288.0,809.0>> = 13.186123471679618
	* W (U+0057): L<<407.0,809.0>--<471.0,341.0>>/L<<471.0,341.0>--<520.0,810.0>> = 13.751505055885556
	* Wacute (U+1E82): L<<179.0,810.0>--<227.0,338.0>>/L<<227.0,338.0>--<288.0,809.0>> = 13.186123471679618
	* Wacute (U+1E82): L<<407.0,809.0>--<471.0,341.0>>/L<<471.0,341.0>--<520.0,810.0>> = 13.751505055885556
	* Wcircumflex (U+0174): L<<179.0,810.0>--<227.0,338.0>>/L<<227.0,338.0>--<288.0,809.0>> = 13.186123471679618
	* Wcircumflex (U+0174): L<<407.0,809.0>--<471.0,341.0>>/L<<471.0,341.0>--<520.0,810.0>> = 13.751505055885556
	* Wdieresis (U+1E84): L<<179.0,810.0>--<227.0,338.0>>/L<<227.0,338.0>--<288.0,809.0>> = 13.186123471679618
	* Wdieresis (U+1E84): L<<407.0,809.0>--<471.0,341.0>>/L<<471.0,341.0>--<520.0,810.0>> = 13.751505055885556 and 15 more. [code: found-jaggy-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * bar (U+007C): L<<64.0,-180.0>--<65.0,810.0>>
 * bracketleft (U+005B): L<<51.0,-185.0>--<52.0,810.0>>
 * bracketright (U+005D): L<<145.0,-122.0>--<144.0,747.0>>
 * bracketright (U+005D): L<<272.0,810.0>--<273.0,-185.0>>
 * lira (U+20A4): L<<238.0,487.0>--<357.0,486.0>>
 * onequarter (U+00BC): L<<628.0,177.0>--<627.0,310.0>>
 * threequarters (U+00BE): L<<710.0,177.0>--<709.0,310.0>>
 * uni00B5 (U+00B5): L<<42.0,-187.0>--<41.0,578.0>>
 * uni0122 (U+0122): L<<368.0,-69.0>--<367.0,-199.0>>
 * uni0123 (U+0123): L<<174.0,645.0>--<175.0,775.0>> and 21 more. [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[14] Oswald-Medium.ttf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Font has old ttfautohint applied?</summary>

* [com.google.fonts/check/old_ttfautohint](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/old_ttfautohint)
<pre>--- Rationale ---
Check if font has been hinted with an outdated version of ttfautohint.</pre>

* ⚠ **WARN** ttfautohint used in font = 1.8.3; latest = 1.8.4; Need to re-run with the newer version! [code: old-ttfa]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [Oslash, Oslashacute, Tbar, Ustraitstrokecy, colonmonetary, emptyset, franc, lira, oslash, oslashacute, tbar, uni01E4, uni01E5, uni0452, uni0462, uni0463, uni046A, uni046B, uni0492, uni0493, uni0496, uni049A, uni04A2, uni04C9, uni04E8, uni04E9, uni20A6, uni20A9, uni20AD, uni20B1, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, ustraitstrokecy]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---
Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will only
differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.
However, a quotedbl should have 2 contours, unless the font belongs to a display
family.
This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: uogonek	Contours detected: 2	Expected: 1
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni01EA	Contours detected: 3	Expected: 2
Glyph name: uni01EB	Contours detected: 3	Expected: 2
Glyph name: uni01F5	Contours detected: 4	Expected: 3
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: fi	Contours detected: 2	Expected: 3
Glyph name: fl	Contours detected: 1	Expected: 2
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: uogonek	Contours detected: 2	Expected: 1 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* exclam (U+0021): X=50.0,Y=809.0 (should be at cap-height 810?)
	* exclam (U+0021): X=186.0,Y=809.0 (should be at cap-height 810?)
	* percent (U+0025): X=548.0,Y=811.0 (should be at cap-height 810?)
	* percent (U+0025): X=639.0,Y=811.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=166.0,Y=809.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=268.0,Y=809.0 (should be at cap-height 810?)
	* J (U+004A): X=192.5,Y=2.0 (should be at baseline 0?)
	* W (U+0057): X=306.0,Y=808.0 (should be at cap-height 810?)
	* W (U+0057): X=406.0,Y=808.0 (should be at cap-height 810?)
	* k (U+006B): X=54.0,Y=1.0 (should be at baseline 0?) and 61 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* partialdiff (U+2202): L<<184.0,374.0>--<164.0,168.0>> -> L<<164.0,168.0>--<164.0,154.0>>
	* uni040E (U+040E): L<<158.0,810.0>--<227.0,471.0>> -> L<<227.0,471.0>--<264.0,235.0>>
	* uni040E (U+040E): L<<264.0,235.0>--<294.0,471.0>> -> L<<294.0,471.0>--<354.0,810.0>>
	* uni0423 (U+0423): L<<158.0,810.0>--<227.0,471.0>> -> L<<227.0,471.0>--<264.0,235.0>>
	* uni0423 (U+0423): L<<264.0,235.0>--<294.0,471.0>> -> L<<294.0,471.0>--<354.0,810.0>>
	* uni04EE (U+04EE): L<<158.0,810.0>--<227.0,471.0>> -> L<<227.0,471.0>--<264.0,235.0>>
	* uni04EE (U+04EE): L<<264.0,235.0>--<294.0,471.0>> -> L<<294.0,471.0>--<354.0,810.0>>
	* uni04F0 (U+04F0): L<<158.0,810.0>--<227.0,471.0>> -> L<<227.0,471.0>--<264.0,235.0>>
	* uni04F0 (U+04F0): L<<264.0,235.0>--<294.0,471.0>> -> L<<294.0,471.0>--<354.0,810.0>>
	* uni04F2 (U+04F2): L<<158.0,810.0>--<227.0,471.0>> -> L<<227.0,471.0>--<264.0,235.0>> and uni04F2 (U+04F2): L<<264.0,235.0>--<294.0,471.0>> -> L<<294.0,471.0>--<354.0,810.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---
This check heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed up
by manual inspection.</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* M (U+004D): L<<298.0,0.0>--<181.0,565.0>>/L<<181.0,565.0>--<170.0,0.0>> = 12.814780858650376
	* M (U+004D): L<<514.0,0.0>--<502.0,563.0>>/L<<502.0,563.0>--<387.0,0.0>> = 12.765629189819022
	* uni041C (U+041C): L<<298.0,0.0>--<181.0,565.0>>/L<<181.0,565.0>--<170.0,0.0>> = 12.814780858650376
	* uni041C (U+041C): L<<514.0,0.0>--<502.0,563.0>>/L<<502.0,563.0>--<387.0,0.0>> = 12.765629189819022
	* uni04CD (U+04CD): L<<298.0,0.0>--<181.0,565.0>>/L<<181.0,565.0>--<170.0,0.0>> = 12.814780858650376
	* uni04CD (U+04CD): L<<514.0,0.0>--<502.0,563.0>>/L<<502.0,563.0>--<387.0,0.0>> = 12.765629189819022
	* uni1E40 (U+1E40): L<<298.0,0.0>--<181.0,565.0>>/L<<181.0,565.0>--<170.0,0.0>> = 12.814780858650376 and uni1E40 (U+1E40): L<<514.0,0.0>--<502.0,563.0>>/L<<502.0,563.0>--<387.0,0.0>> = 12.765629189819022 [code: found-jaggy-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * bracketleft (U+005B): L<<175.0,751.0>--<174.0,-125.0>>
 * lira (U+20A4): L<<203.0,481.0>--<323.0,480.0>>
 * onequarter (U+00BC): L<<652.0,173.0>--<651.0,312.0>>
 * radical (U+221A): L<<127.0,495.0>--<11.0,494.0>>
 * threequarters (U+00BE): L<<713.0,173.0>--<712.0,312.0>>
 * uni0123 (U+0123): L<<170.0,642.0>--<171.0,759.0>>
 * uni043C (U+043C): L<<502.0,578.0>--<506.0,0.0>>
 * uni043C (U+043C): L<<51.0,0.0>--<54.0,578.0>>
 * uni04CE (U+04CE): L<<502.0,578.0>--<505.0,88.0>>
 * uni04CE (U+04CE): L<<51.0,0.0>--<54.0,578.0>>
 * uni0526 (U+0526): L<<612.0,101.0>--<613.0,-154.0>> and uni2074 (U+2074): L<<245.0,606.0>--<244.0,745.0>> [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[13] Oswald-Regular.ttf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Font has old ttfautohint applied?</summary>

* [com.google.fonts/check/old_ttfautohint](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/old_ttfautohint)
<pre>--- Rationale ---
Check if font has been hinted with an outdated version of ttfautohint.</pre>

* ⚠ **WARN** ttfautohint used in font = 1.8.3; latest = 1.8.4; Need to re-run with the newer version! [code: old-ttfa]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [Oslash, Oslashacute, Tbar, Ustraitstrokecy, colonmonetary, emptyset, franc, g, gbreve, gcaron, gcircumflex, gdotaccent, lira, oslash, oslashacute, uni0123, uni01E5, uni01F5, uni0402, uni0462, uni0463, uni046A, uni046B, uni0492, uni0493, uni04E8, uni04E9, uni20A6, uni20A9, uni20AD, uni20B1, uni20B9, uni20BA, uni20BC, uni2113, uni2116]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---
Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will only
differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.
However, a quotedbl should have 2 contours, unless the font belongs to a display
family.
This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: uogonek	Contours detected: 2	Expected: 1
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni01EA	Contours detected: 3	Expected: 2
Glyph name: uni01EB	Contours detected: 3	Expected: 2
Glyph name: uni01F5	Contours detected: 4	Expected: 3
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: fi	Contours detected: 2	Expected: 3
Glyph name: fl	Contours detected: 1	Expected: 2
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: uogonek	Contours detected: 2	Expected: 1 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* partialdiff (U+2202): L<<150.0,362.0>--<134.0,187.0>> -> L<<134.0,187.0>--<134.0,167.0>>
	* uni040E (U+040E): L<<126.0,810.0>--<194.0,465.0>> -> L<<194.0,465.0>--<235.0,208.0>>
	* uni040E (U+040E): L<<235.0,208.0>--<271.0,463.0>> -> L<<271.0,463.0>--<332.0,810.0>>
	* uni0423 (U+0423): L<<126.0,810.0>--<194.0,465.0>> -> L<<194.0,465.0>--<235.0,208.0>>
	* uni0423 (U+0423): L<<235.0,208.0>--<271.0,463.0>> -> L<<271.0,463.0>--<332.0,810.0>>
	* uni04EE (U+04EE): L<<126.0,810.0>--<194.0,465.0>> -> L<<194.0,465.0>--<235.0,208.0>>
	* uni04EE (U+04EE): L<<235.0,208.0>--<271.0,463.0>> -> L<<271.0,463.0>--<332.0,810.0>>
	* uni04F0 (U+04F0): L<<126.0,810.0>--<194.0,465.0>> -> L<<194.0,465.0>--<235.0,208.0>>
	* uni04F0 (U+04F0): L<<235.0,208.0>--<271.0,463.0>> -> L<<271.0,463.0>--<332.0,810.0>>
	* uni04F2 (U+04F2): L<<126.0,810.0>--<194.0,465.0>> -> L<<194.0,465.0>--<235.0,208.0>> and uni04F2 (U+04F2): L<<235.0,208.0>--<271.0,463.0>> -> L<<271.0,463.0>--<332.0,810.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---
This check heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed up
by manual inspection.</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* M (U+004D): L<<298.0,0.0>--<162.0,588.0>>/L<<162.0,588.0>--<153.0,0.0>> = 13.899987412035609
	* M (U+004D): L<<508.0,0.0>--<499.0,588.0>>/L<<499.0,588.0>--<362.0,0.0>> = 13.992446545211042
	* uni041C (U+041C): L<<298.0,0.0>--<162.0,588.0>>/L<<162.0,588.0>--<153.0,0.0>> = 13.899987412035609
	* uni041C (U+041C): L<<508.0,0.0>--<499.0,588.0>>/L<<499.0,588.0>--<362.0,0.0>> = 13.992446545211042
	* uni04CD (U+04CD): L<<298.0,0.0>--<162.0,588.0>>/L<<162.0,588.0>--<153.0,0.0>> = 13.899987412035609
	* uni04CD (U+04CD): L<<508.0,0.0>--<499.0,588.0>>/L<<499.0,588.0>--<362.0,0.0>> = 13.992446545211042
	* uni1E40 (U+1E40): L<<298.0,0.0>--<162.0,588.0>>/L<<162.0,588.0>--<153.0,0.0>> = 13.899987412035609 and uni1E40 (U+1E40): L<<508.0,0.0>--<499.0,588.0>>/L<<499.0,588.0>--<362.0,0.0>> = 13.992446545211042 [code: found-jaggy-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * bar (U+007C): L<<69.0,-148.0>--<70.0,810.0>>
 * onequarter (U+00BC): L<<677.0,168.0>--<676.0,314.0>>
 * threequarters (U+00BE): L<<718.0,168.0>--<717.0,314.0>>
 * uni00B5 (U+00B5): L<<51.0,-175.0>--<50.0,578.0>>
 * uni049A (U+049A): L<<517.0,81.0>--<516.0,-147.0>> and uni2074 (U+2074): L<<250.0,601.0>--<249.0,747.0>> [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[14] Oswald-SemiBold.ttf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Font has old ttfautohint applied?</summary>

* [com.google.fonts/check/old_ttfautohint](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/old_ttfautohint)
<pre>--- Rationale ---
Check if font has been hinted with an outdated version of ttfautohint.</pre>

* ⚠ **WARN** ttfautohint used in font = 1.8.3; latest = 1.8.4; Need to re-run with the newer version! [code: old-ttfa]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [Oslash, Oslashacute, Tbar, Ustraitstrokecy, colonmonetary, emptyset, franc, lira, oslash, oslashacute, tbar, uni01E4, uni01E5, uni0452, uni045B, uni0462, uni0463, uni046A, uni046B, uni0492, uni0493, uni04A2, uni04E8, uni04E9, uni20A6, uni20A9, uni20AD, uni20B1, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, ustraitstrokecy]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---
Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will only
differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.
However, a quotedbl should have 2 contours, unless the font belongs to a display
family.
This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: uogonek	Contours detected: 2	Expected: 1
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni01EA	Contours detected: 3	Expected: 2
Glyph name: uni01EB	Contours detected: 3	Expected: 2
Glyph name: uni01F5	Contours detected: 4	Expected: 3
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: fi	Contours detected: 2	Expected: 3
Glyph name: fl	Contours detected: 1	Expected: 2
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: uogonek	Contours detected: 2	Expected: 1 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* exclam (U+0021): X=49.0,Y=808.0 (should be at cap-height 810?)
	* exclam (U+0021): X=200.0,Y=808.0 (should be at cap-height 810?)
	* percent (U+0025): X=225.0,Y=812.0 (should be at cap-height 810?)
	* percent (U+0025): X=755.0,Y=-2.0 (should be at baseline 0?)
	* percent (U+0025): X=755.0,Y=-2.0 (should be at baseline 0?)
	* at (U+0040): X=681.0,Y=-1.0 (should be at baseline 0?)
	* J (U+004A): X=204.5,Y=2.0 (should be at baseline 0?)
	* W (U+0057): X=296.0,Y=809.0 (should be at cap-height 810?)
	* W (U+0057): X=407.0,Y=809.0 (should be at cap-height 810?)
	* g (U+0067): X=412.0,Y=577.5 (should be at x-height 578?) and 84 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* partialdiff (U+2202): L<<201.0,380.0>--<180.0,158.0>> -> L<<180.0,158.0>--<180.0,147.0>>
	* uni040E (U+040E): L<<175.0,810.0>--<244.0,475.0>> -> L<<244.0,475.0>--<279.0,249.0>>
	* uni040E (U+040E): L<<279.0,249.0>--<306.0,475.0>> -> L<<306.0,475.0>--<365.0,810.0>>
	* uni0423 (U+0423): L<<175.0,810.0>--<244.0,475.0>> -> L<<244.0,475.0>--<279.0,249.0>>
	* uni0423 (U+0423): L<<279.0,249.0>--<306.0,475.0>> -> L<<306.0,475.0>--<365.0,810.0>>
	* uni04EE (U+04EE): L<<175.0,810.0>--<244.0,475.0>> -> L<<244.0,475.0>--<279.0,249.0>>
	* uni04EE (U+04EE): L<<279.0,249.0>--<306.0,475.0>> -> L<<306.0,475.0>--<365.0,810.0>>
	* uni04F0 (U+04F0): L<<175.0,810.0>--<244.0,475.0>> -> L<<244.0,475.0>--<279.0,249.0>>
	* uni04F0 (U+04F0): L<<279.0,249.0>--<306.0,475.0>> -> L<<306.0,475.0>--<365.0,810.0>>
	* uni04F2 (U+04F2): L<<175.0,810.0>--<244.0,475.0>> -> L<<244.0,475.0>--<279.0,249.0>> and uni04F2 (U+04F2): L<<279.0,249.0>--<306.0,475.0>> -> L<<306.0,475.0>--<365.0,810.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---
This check heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed up
by manual inspection.</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* M (U+004D): L<<298.0,0.0>--<191.0,553.0>>/L<<191.0,553.0>--<179.0,0.0>> = 12.193954023697039
	* M (U+004D): L<<517.0,0.0>--<504.0,550.0>>/L<<504.0,550.0>--<400.0,0.0>> = 12.061698239695692
	* colonmonetary (U+20A1): B<<377.0,593.0>-<377.0,599.0>-<377.0,605.0>>/L<<377.0,605.0>--<313.0,109.0>> = 7.352379359892374
	* uni041C (U+041C): L<<298.0,0.0>--<191.0,553.0>>/L<<191.0,553.0>--<179.0,0.0>> = 12.193954023697039
	* uni041C (U+041C): L<<517.0,0.0>--<504.0,550.0>>/L<<504.0,550.0>--<400.0,0.0>> = 12.061698239695692
	* uni04CD (U+04CD): L<<298.0,0.0>--<191.0,553.0>>/L<<191.0,553.0>--<179.0,0.0>> = 12.193954023697039
	* uni04CD (U+04CD): L<<517.0,0.0>--<504.0,550.0>>/L<<504.0,550.0>--<400.0,0.0>> = 12.061698239695692
	* uni1E40 (U+1E40): L<<298.0,0.0>--<191.0,553.0>>/L<<191.0,553.0>--<179.0,0.0>> = 12.193954023697039 and uni1E40 (U+1E40): L<<517.0,0.0>--<504.0,550.0>>/L<<504.0,550.0>--<400.0,0.0>> = 12.061698239695692 [code: found-jaggy-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * bar (U+007C): L<<65.0,-173.0>--<66.0,810.0>>
 * bracketright (U+005D): L<<144.0,-124.0>--<143.0,749.0>>
 * onequarter (U+00BC): L<<639.0,175.0>--<638.0,311.0>>
 * threequarters (U+00BE): L<<712.0,175.0>--<711.0,311.0>>
 * uni00B5 (U+00B5): L<<44.0,-184.0>--<43.0,578.0>>
 * uni040A (U+040A): L<<538.0,0.0>--<358.0,1.0>>
 * uni043C (U+043C): L<<50.0,0.0>--<53.0,578.0>>
 * uni043C (U+043C): L<<517.0,578.0>--<520.0,0.0>>
 * uni049A (U+049A): L<<573.0,112.0>--<572.0,-169.0>>
 * uni04CE (U+04CE): L<<50.0,0.0>--<53.0,578.0>> and 3 more. [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[13] Oswald-ExtraLight.ttf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Font has old ttfautohint applied?</summary>

* [com.google.fonts/check/old_ttfautohint](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/old_ttfautohint)
<pre>--- Rationale ---
Check if font has been hinted with an outdated version of ttfautohint.</pre>

* ⚠ **WARN** ttfautohint used in font = 1.8.3; latest = 1.8.4; Need to re-run with the newer version! [code: old-ttfa]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [uni20A6, uni20A9, uni20B1, uni2116]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---
Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will only
differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.
However, a quotedbl should have 2 contours, unless the font belongs to a display
family.
This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: uogonek	Contours detected: 2	Expected: 1
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni01EA	Contours detected: 3	Expected: 2
Glyph name: uni01EB	Contours detected: 3	Expected: 2
Glyph name: uni01F5	Contours detected: 4	Expected: 3
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: Uhorn	Contours detected: 2	Expected: 1
Glyph name: Uogonek	Contours detected: 2	Expected: 1
Glyph name: aogonek	Contours detected: 3	Expected: 2
Glyph name: eogonek	Contours detected: 3	Expected: 2
Glyph name: fi	Contours detected: 2	Expected: 3
Glyph name: fl	Contours detected: 1	Expected: 2
Glyph name: ohorn	Contours detected: 3	Expected: 2
Glyph name: uhorn	Contours detected: 2	Expected: 1
Glyph name: uni01E5	Contours detected: 4	Expected: 2
Glyph name: uni04BE	Contours detected: 4	Expected: 2 or 3
Glyph name: uni04BF	Contours detected: 4	Expected: 2 or 3
Glyph name: uni1EDB	Contours detected: 4	Expected: 3
Glyph name: uni1EDD	Contours detected: 4	Expected: 3
Glyph name: uni1EDF	Contours detected: 4	Expected: 3
Glyph name: uni1EE1	Contours detected: 4	Expected: 3
Glyph name: uni1EE3	Contours detected: 4	Expected: 3
Glyph name: uni1EE8	Contours detected: 3	Expected: 2
Glyph name: uni1EE9	Contours detected: 3	Expected: 2
Glyph name: uni1EEA	Contours detected: 3	Expected: 2
Glyph name: uni1EEB	Contours detected: 3	Expected: 2
Glyph name: uni1EEC	Contours detected: 3	Expected: 2
Glyph name: uni1EED	Contours detected: 3	Expected: 2
Glyph name: uni1EEE	Contours detected: 3	Expected: 2
Glyph name: uni1EEF	Contours detected: 3	Expected: 2
Glyph name: uni1EF0	Contours detected: 3	Expected: 2
Glyph name: uni1EF1	Contours detected: 3	Expected: 2
Glyph name: uogonek	Contours detected: 2	Expected: 1 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* parenleft (U+0028): X=102.0,Y=-2.0 (should be at baseline 0?)
	* parenright (U+0029): X=165.0,Y=-1.5 (should be at baseline 0?)
	* asterisk (U+002A): X=162.0,Y=809.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=205.0,Y=809.0 (should be at cap-height 810?)
	* at (U+0040): X=435.0,Y=809.0 (should be at cap-height 810?)
	* J (U+004A): X=8.0,Y=-2.0 (should be at baseline 0?)
	* Q (U+0051): X=333.0,Y=-1.0 (should be at baseline 0?)
	* g (U+0067): X=297.0,Y=-1.0 (should be at baseline 0?)
	* m (U+006D): X=520.0,Y=577.0 (should be at x-height 578?)
	* braceleft (U+007B): X=146.5,Y=810.5 (should be at cap-height 810?) and 33 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* uni040E (U+040E): L<<241.0,173.0>--<295.0,438.0>> -> L<<295.0,438.0>--<376.0,810.0>>
	* uni040E (U+040E): L<<87.0,810.0>--<179.0,436.0>> -> L<<179.0,436.0>--<241.0,173.0>>
	* uni0423 (U+0423): L<<241.0,173.0>--<295.0,438.0>> -> L<<295.0,438.0>--<376.0,810.0>>
	* uni0423 (U+0423): L<<87.0,810.0>--<179.0,436.0>> -> L<<179.0,436.0>--<241.0,173.0>>
	* uni04EE (U+04EE): L<<241.0,173.0>--<295.0,438.0>> -> L<<295.0,438.0>--<376.0,810.0>>
	* uni04EE (U+04EE): L<<87.0,810.0>--<179.0,436.0>> -> L<<179.0,436.0>--<241.0,173.0>>
	* uni04F0 (U+04F0): L<<241.0,173.0>--<295.0,438.0>> -> L<<295.0,438.0>--<376.0,810.0>>
	* uni04F0 (U+04F0): L<<87.0,810.0>--<179.0,436.0>> -> L<<179.0,436.0>--<241.0,173.0>>
	* uni04F2 (U+04F2): L<<241.0,173.0>--<295.0,438.0>> -> L<<295.0,438.0>--<376.0,810.0>> and uni04F2 (U+04F2): L<<87.0,810.0>--<179.0,436.0>> -> L<<179.0,436.0>--<241.0,173.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * five (U+0035): L<<133.0,764.0>--<131.0,449.0>>
 * onequarter (U+00BC): L<<563.0,168.0>--<562.0,359.0>>
 * threequarters (U+00BE): L<<640.0,168.0>--<639.0,359.0>>
 * uni043C (U+043C): L<<101.0,441.0>--<99.0,0.0>>
 * uni043C (U+043C): L<<377.0,0.0>--<375.0,443.0>>
 * uni043C (U+043C): L<<419.0,578.0>--<423.0,0.0>>
 * uni043C (U+043C): L<<52.0,0.0>--<57.0,578.0>>
 * uni04CE (U+04CE): L<<101.0,441.0>--<99.0,0.0>>
 * uni04CE (U+04CE): L<<377.0,0.0>--<375.0,443.0>>
 * uni04CE (U+04CE): L<<419.0,578.0>--<423.0,37.0>>
 * uni04CE (U+04CE): L<<52.0,0.0>--<57.0,578.0>> and uni2074 (U+2074): L<<202.0,601.0>--<201.0,792.0>> [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[13] Oswald-Regular.otf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [.notdef, A, AE, AEacute, Aacute, Abreve, Acircumflex, Adieresis, Agrave, Amacron, Aogonek, Aring, Aringacute, Atilde, B, C, Cacute, Ccaron, Ccedilla, Ccircumflex, Cdotaccent, D, Dcaron, Dcroat, E, Eacute, Ebreve, Ecaron, Ecircumflex, Edieresis, Edotaccent, Egrave, Emacron, Eng, Eogonek, Eth, Euro, F, G, Gbreve, Gcaron, Gcircumflex, Gdotaccent, H, Hbar, Hcircumflex, I, IJ, Iacute, Ibreve, Icircumflex, Idieresis, Idotaccent, Igrave, Imacron, Iogonek, Itilde, J, Jcircumflex, K, L, Lacute, Lcaron, Ldot, Lslash, M, N, Nacute, Ncaron, Ntilde, O, OE, Oacute, Obreve, Ocircumflex, Odieresis, Ograve, Ohorn, Ohungarumlaut, Omacron, Oslash, Oslashacute, Otilde, P, Pi, Q, R, Racute, Rcaron, S, Sacute, Scaron, Scedilla, Scircumflex, T, Tbar, Tcaron, Thorn, U, Uacute, Ubreve, Ucircumflex, Udieresis, Ugrave, Uhorn, Uhungarumlaut, Umacron, Uogonek, Uring, Ustraitcy, Ustraitstrokecy, Utilde, V, W, Wacute, Wcircumflex, Wdieresis, Wgrave, X, Y, Yacute, Ycircumflex, Ydieresis, Ygrave, Z, Zacute, Zcaron, Zdotaccent, a, aacute, abreve, acircumflex, acute, acutecomb, adieresis, ae, aeacute, agrave, amacron, ampersand, aogonek, approxequal, aring, aringacute, asciicircum, asciitilde, asterisk, at, atilde, b, backslash, bar, braceleft, braceright, bracketleft, bracketright, breve, brokenbar, bullet, c, cacute, caron, ccaron, ccedilla, ccircumflex, cdotaccent, cedilla, cent, circumflex, colon, colonmonetary, comma, copyright, currency, d, dagger, daggerdbl, dcaron, dcroat, degree, dieresis, divide, dollar, dong, dotaccent, dotbelowcomb, dotlessi, e, eacute, ebreve, ecaron, ecircumflex, edieresis, edotaccent, egrave, eight, ellipsis, emacron, emdash, emptyset, endash, eng, eogonek, equal, estimated, eth, exclam, exclamdown, f, f_f, f_f_i, f_f_ij, f_f_l, f_ij, fi, five, fl, florin, four, fraction, franc, g, gbreve, gcaron, gcircumflex, gdotaccent, germandbls, grave, gravecomb, greater, greaterequal, guillemotleft, guillemotright, guilsinglleft, guilsinglright, h, hbar, hcircumflex, hookabovecomb, hungarumlaut, hyphen, i, i.loclTRK, iacute, ibreve, icircumflex, idieresis, igrave, ij, imacron, infinity, integral, iogonek, itilde, j, jcircumflex, k, kgreenlandic, l, lacute, lcaron, ldot, less, lessequal, lira, logicalnot, longs, lozenge, lslash, m, macron, minus, minute, multiply, n, nacute, napostrophe, ncaron, nine, notequal, ntilde, numbersign, o, oacute, obreve, ocircumflex, odieresis, oe, ogonek, ograve, ohorn, ohungarumlaut, omacron, one, onehalf, onequarter, ordfeminine, ordmasculine, oslash, oslashacute, otilde, p, paragraph, parenleft, parenright, partialdiff, percent, period, periodcentered, periodcentered.loclCAT, perthousand, peseta, pi, plus, plusminus, product, q, question, questiondown, quotedbl, quotedblbase, quotedblleft, quotedblright, quoteleft, quoteright, quotesinglbase, quotesingle, r, racute, radical, rcaron, registered, ring, s, sacute, scaron, scedilla, scircumflex, second, section, semicolon, seven, six, slash, sterling, summation, t, tbar, tcaron, thorn, three, threequarters, tilde, tildecomb, trademark, two, u, uacute, ubreve, ucircumflex, udieresis, ugrave, uhorn, uhungarumlaut, umacron, underscore, uni00AD, uni00B2, uni00B3, uni00B5, uni00B9, uni0122, uni0123, uni0136, uni0137, uni013B, uni013C, uni0145, uni0146, uni0156, uni0157, uni0162, uni0163, uni018F, uni01B7, uni01C4, uni01C5, uni01C6, uni01C7, uni01C8, uni01C9, uni01CA, uni01CB, uni01CC, uni01CD, uni01CE, uni01D3, uni01D4, uni01E4, uni01E5, uni01E8, uni01E9, uni01EA, uni01EB, uni01EE, uni01EF, uni01F1, uni01F2, uni01F3, uni01F4, uni01F5, uni0200, uni0201, uni0202, uni0203, uni0204, uni0205, uni0206, uni0207, uni0208, uni0209, uni020A, uni020B, uni020C, uni020D, uni020E, uni020F, uni0210, uni0211, uni0212, uni0213, uni0214, uni0215, uni0216, uni0217, uni0218, uni0219, uni021A, uni021B, uni021E, uni021F, uni022A, uni022B, uni022C, uni022D, uni0230, uni0231, uni0232, uni0233, uni0237, uni0259, uni0292, uni02BC, uni02C9, uni0302, uni0302.case, uni03020300, uni03020301, uni03020303, uni03020309, uni0304, uni0306, uni03060300, uni03060301, uni03060303, uni03060309, uni0307, uni0308, uni030A, uni030B, uni030C, uni030C.alt, uni030F, uni0311, uni0312, uni031B, uni031B.case, uni0324, uni0326, uni0326.alt, uni0327, uni0328, uni032E, uni0331, uni0335, uni0400, uni0401, uni0402, uni0403, uni0404, uni0405, uni0406, uni0407, uni0408, uni0409, uni040A, uni040B, uni040C, uni040D, uni040E, uni040F, uni0410, uni0411, uni0412, uni0413, uni0414, uni0415, uni0416, uni0417, uni0418, uni0419, uni041A, uni041B, uni041C, uni041D, uni041E, uni041F, uni0420, uni0421, uni0422, uni0423, uni0424, uni0425, uni0426, uni0427, uni0428, uni0429, uni042A, uni042B, uni042C, uni042D, uni042E, uni042F, uni0430, uni0431, uni0432, uni0433, uni0434, uni0435, uni0436, uni0437, uni0438, uni0439, uni043A, uni043B, uni043C, uni043D, uni043E, uni043F, uni0440, uni0441, uni0442, uni0443, uni0444, uni0445, uni0446, uni0447, uni0448, uni0449, uni044A, uni044B, uni044C, uni044D, uni044E, uni044F, uni0450, uni0451, uni0452, uni0453, uni0454, uni0455, uni0456, uni0457, uni0458, uni0459, uni045A, uni045B, uni045C, uni045D, uni045E, uni045F, uni0462, uni0463, uni046A, uni046B, uni0490, uni0491, uni0492, uni0493, uni0496, uni0497, uni049A, uni049B, uni04A2, uni04A3, uni04BA, uni04BB, uni04C9, uni04CA, uni04D8, uni04D9, uni04E8, uni04E9, uni1E02, uni1E03, uni1E0A, uni1E0B, uni1E1E, uni1E1F, uni1E40, uni1E41, uni1E56, uni1E57, uni1E60, uni1E61, uni1E6A, uni1E6B, uni1E9E, uni1EA0, uni1EA1, uni1EA2, uni1EA3, uni1EA4, uni1EA5, uni1EA6, uni1EA7, uni1EA8, uni1EA9, uni1EAA, uni1EAB, uni1EAC, uni1EAD, uni1EAE, uni1EAF, uni1EB0, uni1EB1, uni1EB2, uni1EB3, uni1EB4, uni1EB5, uni1EB6, uni1EB7, uni1EB8, uni1EB9, uni1EBA, uni1EBB, uni1EBC, uni1EBD, uni1EBE, uni1EBF, uni1EC0, uni1EC1, uni1EC2, uni1EC3, uni1EC4, uni1EC5, uni1EC6, uni1EC7, uni1EC8, uni1EC9, uni1ECA, uni1ECB, uni1ECC, uni1ECD, uni1ECE, uni1ECF, uni1ED0, uni1ED1, uni1ED2, uni1ED3, uni1ED4, uni1ED5, uni1ED6, uni1ED7, uni1ED8, uni1ED9, uni1EDA, uni1EDB, uni1EDC, uni1EDD, uni1EDE, uni1EDF, uni1EE0, uni1EE1, uni1EE2, uni1EE3, uni1EE4, uni1EE5, uni1EE6, uni1EE7, uni1EE8, uni1EE9, uni1EEA, uni1EEB, uni1EEC, uni1EED, uni1EEE, uni1EEF, uni1EF0, uni1EF1, uni1EF4, uni1EF5, uni1EF6, uni1EF7, uni1EF8, uni1EF9, uni2010, uni2052, uni2074, uni20A6, uni20A9, uni20AD, uni20B1, uni20B2, uni20B5, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, uni212A, uni212B, uni2215, uni2219, uni27E8, uni27E9, uogonek, uring, ustraitcy, ustraitstrokecy, utilde, v, w, wacute, wcircumflex, wdieresis, wgrave, x, y, yacute, ycircumflex, ydieresis, yen, ygrave, z, zacute, zcaron, zdotaccent, zero]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* percent (U+0025): X=604.0,Y=811.0 (should be at cap-height 810?)
	* percent (U+0025): X=512.0,Y=811.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=253.0,Y=809.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=172.0,Y=809.0 (should be at cap-height 810?)
	* comma (U+002C): X=151.0,Y=2.0 (should be at baseline 0?)
	* semicolon (U+003B): X=58.0,Y=1.0 (should be at baseline 0?)
	* k (U+006B): X=56.0,Y=1.0 (should be at baseline 0?)
	* k (U+006B): X=163.0,Y=1.0 (should be at baseline 0?)
	* k (U+006B): X=163.0,Y=811.0 (should be at cap-height 810?)
	* k (U+006B): X=56.0,Y=811.0 (should be at cap-height 810?) and 78 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are any segments inordinately short?</summary>

* [com.google.fonts/check/outline_short_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_short_segments)
<pre>--- Rationale ---
This check looks for outline segments which seem particularly short (less than
0.6% of the overall path length).
This check is not run for variable fonts, as they may legitimately have short
segments. As this check is liable to generate significant numbers of false
positives, it will pass if there are more than 100 reported short segments.</pre>

* ⚠ **WARN** The following glyphs have segments which seem very short:
	* three (U+0033) contains a short segment L<<146.0,583.0>--<146.0,600.0>>
	* three (U+0033) contains a short segment B<<210.0,379.0>-<214.0,379.0>-<221.0,379.0>-<225.0,378.0>>
	* six (U+0036) contains a short segment B<<456.0,608.0>-<456.0,612.0>-<455.0,617.0>-<455.0,620.0>>
	* nine (U+0039) contains a short segment L<<46.0,201.0>--<46.0,192.0>>
	* at (U+0040) contains a short segment L<<589.0,596.0>--<579.0,579.0>>
	* y (U+0079) contains a short segment L<<45.0,-145.0>--<58.0,-145.0>>
	* uni00B3 (U+00B3) contains a short segment L<<157.0,746.0>--<157.0,750.0>>
	* threequarters (U+00BE) contains a short segment L<<138.0,665.0>--<138.0,669.0>>
	* yacute (U+00FD) contains a short segment L<<45.0,-145.0>--<58.0,-145.0>>
	* ydieresis (U+00FF) contains a short segment L<<45.0,-145.0>--<58.0,-145.0>> and 74 more. [code: found-short-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* partialdiff (U+2202): L<<134.0,167.0>--<134.0,187.0>> -> L<<134.0,187.0>--<150.0,362.0>>
	* uni040E (U+040E): L<<235.0,208.0>--<194.0,465.0>> -> L<<194.0,465.0>--<126.0,810.0>>
	* uni040E (U+040E): L<<332.0,810.0>--<271.0,463.0>> -> L<<271.0,463.0>--<235.0,208.0>>
	* uni0423 (U+0423): L<<235.0,208.0>--<194.0,465.0>> -> L<<194.0,465.0>--<126.0,810.0>>
	* uni0423 (U+0423): L<<332.0,810.0>--<271.0,463.0>> -> L<<271.0,463.0>--<235.0,208.0>>
	* uni04EE (U+04EE): L<<235.0,208.0>--<194.0,465.0>> -> L<<194.0,465.0>--<126.0,810.0>>
	* uni04EE (U+04EE): L<<332.0,810.0>--<271.0,463.0>> -> L<<271.0,463.0>--<235.0,208.0>>
	* uni04F0 (U+04F0): L<<235.0,208.0>--<194.0,465.0>> -> L<<194.0,465.0>--<126.0,810.0>>
	* uni04F0 (U+04F0): L<<332.0,810.0>--<271.0,463.0>> -> L<<271.0,463.0>--<235.0,208.0>>
	* uni04F2 (U+04F2): L<<235.0,208.0>--<194.0,465.0>> -> L<<194.0,465.0>--<126.0,810.0>> and uni04F2 (U+04F2): L<<332.0,810.0>--<271.0,463.0>> -> L<<271.0,463.0>--<235.0,208.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---
This check heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed up
by manual inspection.</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* M (U+004D): L<<153.0,0.0>--<162.0,588.0>>/L<<162.0,588.0>--<298.0,0.0>> = 13.899987412035635
	* M (U+004D): L<<362.0,0.0>--<499.0,588.0>>/L<<499.0,588.0>--<508.0,0.0>> = 13.992446545211068
	* uni041C (U+041C): L<<153.0,0.0>--<162.0,588.0>>/L<<162.0,588.0>--<298.0,0.0>> = 13.899987412035635
	* uni041C (U+041C): L<<362.0,0.0>--<499.0,588.0>>/L<<499.0,588.0>--<508.0,0.0>> = 13.992446545211068
	* uni04CD (U+04CD): L<<153.0,0.0>--<162.0,588.0>>/L<<162.0,588.0>--<298.0,0.0>> = 13.899987412035635
	* uni04CD (U+04CD): L<<362.0,0.0>--<499.0,588.0>>/L<<499.0,588.0>--<508.0,0.0>> = 13.992446545211068
	* uni1E40 (U+1E40): L<<153.0,0.0>--<162.0,588.0>>/L<<162.0,588.0>--<298.0,0.0>> = 13.899987412035635 and uni1E40 (U+1E40): L<<362.0,0.0>--<499.0,588.0>>/L<<499.0,588.0>--<508.0,0.0>> = 13.992446545211068 [code: found-jaggy-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * bar (U+007C): L<<70.0,810.0>--<69.0,-148.0>>
 * onequarter (U+00BC): L<<676.0,314.0>--<677.0,168.0>>
 * threequarters (U+00BE): L<<717.0,314.0>--<718.0,168.0>>
 * uni00B5 (U+00B5): L<<50.0,578.0>--<51.0,-175.0>>
 * uni049A (U+049A): L<<516.0,-147.0>--<517.0,81.0>> and uni2074 (U+2074): L<<249.0,747.0>--<250.0,601.0>> [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[13] Oswald-SemiBold.otf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [.notdef, A, AE, AEacute, Aacute, Abreve, Acircumflex, Adieresis, Agrave, Amacron, Aogonek, Aring, Aringacute, Atilde, B, C, Cacute, Ccaron, Ccedilla, Ccircumflex, Cdotaccent, D, Dcaron, Dcroat, E, Eacute, Ebreve, Ecaron, Ecircumflex, Edieresis, Edotaccent, Egrave, Emacron, Eng, Eogonek, Eth, Euro, F, G, Gbreve, Gcaron, Gcircumflex, Gdotaccent, H, Hbar, Hcircumflex, I, IJ, Iacute, Ibreve, Icircumflex, Idieresis, Idotaccent, Igrave, Imacron, Iogonek, Itilde, J, Jcircumflex, K, L, Lacute, Lcaron, Ldot, Lslash, M, N, Nacute, Ncaron, Ntilde, O, OE, Oacute, Obreve, Ocircumflex, Odieresis, Ograve, Ohorn, Ohungarumlaut, Omacron, Oslash, Oslashacute, Otilde, P, Pi, Q, R, Racute, Rcaron, S, Sacute, Scaron, Scedilla, Scircumflex, T, Tbar, Tcaron, Thorn, U, Uacute, Ubreve, Ucircumflex, Udieresis, Ugrave, Uhorn, Uhungarumlaut, Umacron, Uogonek, Uring, Ustraitcy, Ustraitstrokecy, Utilde, V, W, Wacute, Wcircumflex, Wdieresis, Wgrave, X, Y, Yacute, Ycircumflex, Ydieresis, Ygrave, Z, Zacute, Zcaron, Zdotaccent, a, aacute, abreve, acircumflex, acute, acutecomb, adieresis, ae, aeacute, agrave, amacron, ampersand, aogonek, approxequal, aring, aringacute, asciicircum, asciitilde, asterisk, at, atilde, b, backslash, bar, braceleft, braceright, bracketleft, bracketright, breve, brokenbar, bullet, c, cacute, caron, ccaron, ccedilla, ccircumflex, cdotaccent, cedilla, cent, circumflex, colon, colonmonetary, comma, copyright, currency, d, dagger, daggerdbl, dcaron, dcroat, degree, dieresis, divide, dollar, dong, dotaccent, dotbelowcomb, dotlessi, e, eacute, ebreve, ecaron, ecircumflex, edieresis, edotaccent, egrave, eight, ellipsis, emacron, emdash, emptyset, endash, eng, eogonek, equal, estimated, eth, exclam, exclamdown, f, f_f, f_f_i, f_f_ij, f_f_l, f_ij, fi, five, fl, florin, four, fraction, franc, g, gbreve, gcaron, gcircumflex, gdotaccent, germandbls, grave, gravecomb, greater, greaterequal, guillemotleft, guillemotright, guilsinglleft, guilsinglright, h, hbar, hcircumflex, hookabovecomb, hungarumlaut, hyphen, i, i.loclTRK, iacute, ibreve, icircumflex, idieresis, igrave, ij, imacron, infinity, integral, iogonek, itilde, j, jcircumflex, k, kgreenlandic, l, lacute, lcaron, ldot, less, lessequal, lira, logicalnot, longs, lozenge, lslash, m, macron, minus, minute, multiply, n, nacute, napostrophe, ncaron, nine, notequal, ntilde, numbersign, o, oacute, obreve, ocircumflex, odieresis, oe, ogonek, ograve, ohorn, ohungarumlaut, omacron, one, onehalf, onequarter, ordfeminine, ordmasculine, oslash, oslashacute, otilde, p, paragraph, parenleft, parenright, partialdiff, percent, period, periodcentered, periodcentered.loclCAT, perthousand, peseta, pi, plus, plusminus, product, q, question, questiondown, quotedbl, quotedblbase, quotedblleft, quotedblright, quoteleft, quoteright, quotesinglbase, quotesingle, r, racute, radical, rcaron, registered, ring, s, sacute, scaron, scedilla, scircumflex, second, section, semicolon, seven, six, slash, sterling, summation, t, tbar, tcaron, thorn, three, threequarters, tilde, tildecomb, trademark, two, u, uacute, ubreve, ucircumflex, udieresis, ugrave, uhorn, uhungarumlaut, umacron, underscore, uni00AD, uni00B2, uni00B3, uni00B5, uni00B9, uni0122, uni0123, uni0136, uni0137, uni013B, uni013C, uni0145, uni0146, uni0156, uni0157, uni0162, uni0163, uni018F, uni01B7, uni01C4, uni01C5, uni01C6, uni01C7, uni01C8, uni01C9, uni01CA, uni01CB, uni01CC, uni01CD, uni01CE, uni01D3, uni01D4, uni01E4, uni01E5, uni01E8, uni01E9, uni01EA, uni01EB, uni01EE, uni01EF, uni01F1, uni01F2, uni01F3, uni01F4, uni01F5, uni0200, uni0201, uni0202, uni0203, uni0204, uni0205, uni0206, uni0207, uni0208, uni0209, uni020A, uni020B, uni020C, uni020D, uni020E, uni020F, uni0210, uni0211, uni0212, uni0213, uni0214, uni0215, uni0216, uni0217, uni0218, uni0219, uni021A, uni021B, uni021E, uni021F, uni022A, uni022B, uni022C, uni022D, uni0230, uni0231, uni0232, uni0233, uni0237, uni0259, uni0292, uni02BC, uni02C9, uni0302, uni0302.case, uni03020300, uni03020301, uni03020303, uni03020309, uni0304, uni0306, uni03060300, uni03060301, uni03060303, uni03060309, uni0307, uni0308, uni030A, uni030B, uni030C, uni030C.alt, uni030F, uni0311, uni0312, uni031B, uni031B.case, uni0324, uni0326, uni0326.alt, uni0327, uni0328, uni032E, uni0331, uni0335, uni0400, uni0401, uni0402, uni0403, uni0404, uni0405, uni0406, uni0407, uni0408, uni0409, uni040A, uni040B, uni040C, uni040D, uni040E, uni040F, uni0410, uni0411, uni0412, uni0413, uni0414, uni0415, uni0416, uni0417, uni0418, uni0419, uni041A, uni041B, uni041C, uni041D, uni041E, uni041F, uni0420, uni0421, uni0422, uni0423, uni0424, uni0425, uni0426, uni0427, uni0428, uni0429, uni042A, uni042B, uni042C, uni042D, uni042E, uni042F, uni0430, uni0431, uni0432, uni0433, uni0434, uni0435, uni0436, uni0437, uni0438, uni0439, uni043A, uni043B, uni043C, uni043D, uni043E, uni043F, uni0440, uni0441, uni0442, uni0443, uni0444, uni0445, uni0446, uni0447, uni0448, uni0449, uni044A, uni044B, uni044C, uni044D, uni044E, uni044F, uni0450, uni0451, uni0452, uni0453, uni0454, uni0455, uni0456, uni0457, uni0458, uni0459, uni045A, uni045B, uni045C, uni045D, uni045E, uni045F, uni0462, uni0463, uni046A, uni046B, uni0490, uni0491, uni0492, uni0493, uni0496, uni0497, uni049A, uni049B, uni04A2, uni04A3, uni04BA, uni04BB, uni04C9, uni04CA, uni04D8, uni04D9, uni04E8, uni04E9, uni1E02, uni1E03, uni1E0A, uni1E0B, uni1E1E, uni1E1F, uni1E40, uni1E41, uni1E56, uni1E57, uni1E60, uni1E61, uni1E6A, uni1E6B, uni1E9E, uni1EA0, uni1EA1, uni1EA2, uni1EA3, uni1EA4, uni1EA5, uni1EA6, uni1EA7, uni1EA8, uni1EA9, uni1EAA, uni1EAB, uni1EAC, uni1EAD, uni1EAE, uni1EAF, uni1EB0, uni1EB1, uni1EB2, uni1EB3, uni1EB4, uni1EB5, uni1EB6, uni1EB7, uni1EB8, uni1EB9, uni1EBA, uni1EBB, uni1EBC, uni1EBD, uni1EBE, uni1EBF, uni1EC0, uni1EC1, uni1EC2, uni1EC3, uni1EC4, uni1EC5, uni1EC6, uni1EC7, uni1EC8, uni1EC9, uni1ECA, uni1ECB, uni1ECC, uni1ECD, uni1ECE, uni1ECF, uni1ED0, uni1ED1, uni1ED2, uni1ED3, uni1ED4, uni1ED5, uni1ED6, uni1ED7, uni1ED8, uni1ED9, uni1EDA, uni1EDB, uni1EDC, uni1EDD, uni1EDE, uni1EDF, uni1EE0, uni1EE1, uni1EE2, uni1EE3, uni1EE4, uni1EE5, uni1EE6, uni1EE7, uni1EE8, uni1EE9, uni1EEA, uni1EEB, uni1EEC, uni1EED, uni1EEE, uni1EEF, uni1EF0, uni1EF1, uni1EF4, uni1EF5, uni1EF6, uni1EF7, uni1EF8, uni1EF9, uni2010, uni2052, uni2074, uni20A6, uni20A9, uni20AD, uni20B1, uni20B2, uni20B5, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, uni212A, uni212B, uni2215, uni2219, uni27E8, uni27E9, uogonek, uring, ustraitcy, ustraitstrokecy, utilde, v, w, wacute, wcircumflex, wdieresis, wgrave, x, y, yacute, ycircumflex, ydieresis, yen, ygrave, z, zacute, zcaron, zdotaccent, zero]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* exclam (U+0021): X=200.0,Y=808.0 (should be at cap-height 810?)
	* exclam (U+0021): X=49.0,Y=808.0 (should be at cap-height 810?)
	* percent (U+0025): X=225.0,Y=812.0 (should be at cap-height 810?)
	* percent (U+0025): X=755.0,Y=-2.0 (should be at baseline 0?)
	* percent (U+0025): X=755.0,Y=-2.0 (should be at baseline 0?)
	* at (U+0040): X=681.0,Y=-1.0 (should be at baseline 0?)
	* W (U+0057): X=407.0,Y=809.0 (should be at cap-height 810?)
	* W (U+0057): X=296.0,Y=809.0 (should be at cap-height 810?)
	* t (U+0074): X=320.0,Y=1.0 (should be at baseline 0?)
	* uni00B5 (U+00B5): X=195.0,Y=-1.0 (should be at baseline 0?) and 70 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are any segments inordinately short?</summary>

* [com.google.fonts/check/outline_short_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_short_segments)
<pre>--- Rationale ---
This check looks for outline segments which seem particularly short (less than
0.6% of the overall path length).
This check is not run for variable fonts, as they may legitimately have short
segments. As this check is liable to generate significant numbers of false
positives, it will pass if there are more than 100 reported short segments.</pre>

* ⚠ **WARN** The following glyphs have segments which seem very short:
	* six (U+0036) contains a short segment B<<476.0,601.0>-<476.0,605.0>-<476.0,610.0>-<476.0,615.0>>
	* nine (U+0039) contains a short segment L<<53.0,208.0>--<53.0,196.0>>
	* uni00B3 (U+00B3) contains a short segment L<<189.0,746.0>--<189.0,750.0>>
	* threequarters (U+00BE) contains a short segment L<<169.0,668.0>--<169.0,672.0>>
	* uni01E5 (U+01E5) contains a short segment B<<25.0,-55.0>-<24.0,-60.0>-<24.0,-66.0>-<24.0,-71.0>>
	* uni0402 (U+0402) contains a short segment B<<403.0,91.0>-<397.0,91.0>-<391.0,90.0>-<384.0,91.0>>
	* uni0416 (U+0416) contains a short segment L<<310.0,396.0>--<319.0,396.0>>
	* uni0416 (U+0416) contains a short segment L<<451.0,396.0>--<459.0,396.0>>
	* uni0416 (U+0416) contains a short segment L<<459.0,429.0>--<451.0,429.0>>
	* uni0416 (U+0416) contains a short segment L<<319.0,429.0>--<311.0,429.0>> and 48 more. [code: found-short-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* partialdiff (U+2202): L<<180.0,147.0>--<180.0,158.0>> -> L<<180.0,158.0>--<201.0,380.0>>
	* uni040E (U+040E): L<<279.0,249.0>--<244.0,475.0>> -> L<<244.0,475.0>--<175.0,810.0>>
	* uni040E (U+040E): L<<365.0,810.0>--<306.0,475.0>> -> L<<306.0,475.0>--<279.0,249.0>>
	* uni0423 (U+0423): L<<279.0,249.0>--<244.0,475.0>> -> L<<244.0,475.0>--<175.0,810.0>>
	* uni0423 (U+0423): L<<365.0,810.0>--<306.0,475.0>> -> L<<306.0,475.0>--<279.0,249.0>>
	* uni04EE (U+04EE): L<<279.0,249.0>--<244.0,475.0>> -> L<<244.0,475.0>--<175.0,810.0>>
	* uni04EE (U+04EE): L<<365.0,810.0>--<306.0,475.0>> -> L<<306.0,475.0>--<279.0,249.0>>
	* uni04F0 (U+04F0): L<<279.0,249.0>--<244.0,475.0>> -> L<<244.0,475.0>--<175.0,810.0>>
	* uni04F0 (U+04F0): L<<365.0,810.0>--<306.0,475.0>> -> L<<306.0,475.0>--<279.0,249.0>>
	* uni04F2 (U+04F2): L<<279.0,249.0>--<244.0,475.0>> -> L<<244.0,475.0>--<175.0,810.0>> and uni04F2 (U+04F2): L<<365.0,810.0>--<306.0,475.0>> -> L<<306.0,475.0>--<279.0,249.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---
This check heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed up
by manual inspection.</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* M (U+004D): L<<179.0,0.0>--<191.0,553.0>>/L<<191.0,553.0>--<298.0,0.0>> = 12.193954023697069
	* M (U+004D): L<<400.0,0.0>--<504.0,550.0>>/L<<504.0,550.0>--<517.0,0.0>> = 12.061698239695692
	* colonmonetary (U+20A1): L<<313.0,109.0>--<377.0,605.0>>/B<<377.0,605.0>-<377.0,601.0>-<377.0,597.0>-<377.0,593.0>> = 7.352379359892325
	* uni041C (U+041C): L<<179.0,0.0>--<191.0,553.0>>/L<<191.0,553.0>--<298.0,0.0>> = 12.193954023697069
	* uni041C (U+041C): L<<400.0,0.0>--<504.0,550.0>>/L<<504.0,550.0>--<517.0,0.0>> = 12.061698239695692
	* uni04CD (U+04CD): L<<179.0,0.0>--<191.0,553.0>>/L<<191.0,553.0>--<298.0,0.0>> = 12.193954023697069
	* uni04CD (U+04CD): L<<400.0,0.0>--<504.0,550.0>>/L<<504.0,550.0>--<517.0,0.0>> = 12.061698239695692
	* uni1E40 (U+1E40): L<<179.0,0.0>--<191.0,553.0>>/L<<191.0,553.0>--<298.0,0.0>> = 12.193954023697069 and uni1E40 (U+1E40): L<<400.0,0.0>--<504.0,550.0>>/L<<504.0,550.0>--<517.0,0.0>> = 12.061698239695692 [code: found-jaggy-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * bar (U+007C): L<<66.0,810.0>--<65.0,-173.0>>
 * bracketright (U+005D): L<<143.0,749.0>--<144.0,-124.0>>
 * onequarter (U+00BC): L<<638.0,311.0>--<639.0,175.0>>
 * threequarters (U+00BE): L<<710.0,311.0>--<711.0,175.0>>
 * uni00B5 (U+00B5): L<<43.0,578.0>--<44.0,-184.0>>
 * uni013C (U+013C): L<<206.0,-192.0>--<207.0,-68.0>>
 * uni0145 (U+0145): L<<348.0,-192.0>--<349.0,-68.0>>
 * uni0146 (U+0146): L<<318.0,-192.0>--<319.0,-68.0>>
 * uni0156 (U+0156): L<<363.0,-192.0>--<364.0,-68.0>>
 * uni0218 (U+0218): L<<324.0,-192.0>--<325.0,-68.0>> and 11 more. [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[12] Oswald-ExtraLight.otf</b></summary>
<details>
<summary>🔥 <b>FAIL:</b> Checking OS/2 usWeightClass.</summary>

* [com.google.fonts/check/usweightclass](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/usweightclass)
<pre>--- Rationale ---
Google Fonts expects variable fonts, static ttfs and static otfs to have
differing OS/2 usWeightClass values.
For Variable Fonts, Thin-Black must be 100-900
For static ttfs, Thin-Black can be 100-900 or 250-900
For static otfs, Thin-Black must be 250-900
If static otfs are set lower than 250, text may appear blurry in legacy Windows
applications.
Glyphsapp users can change the usWeightClass value of an instance by adding a
&#x27;weightClass&#x27; customParameter.</pre>

* 🔥 **FAIL** OS/2 usWeightClass is '200' when it should be '275'. [code: bad-value]

</details>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [.notdef, A, AE, AEacute, Aacute, Abreve, Acircumflex, Adieresis, Agrave, Amacron, Aogonek, Aring, Aringacute, Atilde, B, C, Cacute, Ccaron, Ccedilla, Ccircumflex, Cdotaccent, D, Dcaron, Dcroat, E, Eacute, Ebreve, Ecaron, Ecircumflex, Edieresis, Edotaccent, Egrave, Emacron, Eng, Eogonek, Eth, Euro, F, G, Gbreve, Gcaron, Gcircumflex, Gdotaccent, H, Hbar, Hcircumflex, I, IJ, Iacute, Ibreve, Icircumflex, Idieresis, Idotaccent, Igrave, Imacron, Iogonek, Itilde, J, Jcircumflex, K, L, Lacute, Lcaron, Ldot, Lslash, M, N, Nacute, Ncaron, Ntilde, O, OE, Oacute, Obreve, Ocircumflex, Odieresis, Ograve, Ohorn, Ohungarumlaut, Omacron, Oslash, Oslashacute, Otilde, P, Pi, Q, R, Racute, Rcaron, S, Sacute, Scaron, Scedilla, Scircumflex, T, Tbar, Tcaron, Thorn, U, Uacute, Ubreve, Ucircumflex, Udieresis, Ugrave, Uhorn, Uhungarumlaut, Umacron, Uogonek, Uring, Ustraitcy, Ustraitstrokecy, Utilde, V, W, Wacute, Wcircumflex, Wdieresis, Wgrave, X, Y, Yacute, Ycircumflex, Ydieresis, Ygrave, Z, Zacute, Zcaron, Zdotaccent, a, aacute, abreve, acircumflex, acute, acutecomb, adieresis, ae, aeacute, agrave, amacron, ampersand, aogonek, approxequal, aring, aringacute, asciicircum, asciitilde, asterisk, at, atilde, b, backslash, bar, braceleft, braceright, bracketleft, bracketright, breve, brokenbar, bullet, c, cacute, caron, ccaron, ccedilla, ccircumflex, cdotaccent, cedilla, cent, circumflex, colon, colonmonetary, comma, copyright, currency, d, dagger, daggerdbl, dcaron, dcroat, degree, dieresis, divide, dollar, dong, dotaccent, dotbelowcomb, dotlessi, e, eacute, ebreve, ecaron, ecircumflex, edieresis, edotaccent, egrave, eight, ellipsis, emacron, emdash, emptyset, endash, eng, eogonek, equal, estimated, eth, exclam, exclamdown, f, f_f, f_f_i, f_f_ij, f_f_l, f_ij, fi, five, fl, florin, four, fraction, franc, g, gbreve, gcaron, gcircumflex, gdotaccent, germandbls, grave, gravecomb, greater, greaterequal, guillemotleft, guillemotright, guilsinglleft, guilsinglright, h, hbar, hcircumflex, hookabovecomb, hungarumlaut, hyphen, i, i.loclTRK, iacute, ibreve, icircumflex, idieresis, igrave, ij, imacron, infinity, integral, iogonek, itilde, j, jcircumflex, k, kgreenlandic, l, lacute, lcaron, ldot, less, lessequal, lira, logicalnot, longs, lozenge, lslash, m, macron, minus, minute, multiply, n, nacute, napostrophe, ncaron, nine, notequal, ntilde, numbersign, o, oacute, obreve, ocircumflex, odieresis, oe, ogonek, ograve, ohorn, ohungarumlaut, omacron, one, onehalf, onequarter, ordfeminine, ordmasculine, oslash, oslashacute, otilde, p, paragraph, parenleft, parenright, partialdiff, percent, period, periodcentered, periodcentered.loclCAT, perthousand, peseta, pi, plus, plusminus, product, q, question, questiondown, quotedbl, quotedblbase, quotedblleft, quotedblright, quoteleft, quoteright, quotesinglbase, quotesingle, r, racute, radical, rcaron, registered, ring, s, sacute, scaron, scedilla, scircumflex, second, section, semicolon, seven, six, slash, sterling, summation, t, tbar, tcaron, thorn, three, threequarters, tilde, tildecomb, trademark, two, u, uacute, ubreve, ucircumflex, udieresis, ugrave, uhorn, uhungarumlaut, umacron, underscore, uni00AD, uni00B2, uni00B3, uni00B5, uni00B9, uni0122, uni0123, uni0136, uni0137, uni013B, uni013C, uni0145, uni0146, uni0156, uni0157, uni0162, uni0163, uni018F, uni01B7, uni01C4, uni01C5, uni01C6, uni01C7, uni01C8, uni01C9, uni01CA, uni01CB, uni01CC, uni01CD, uni01CE, uni01D3, uni01D4, uni01E4, uni01E5, uni01E8, uni01E9, uni01EA, uni01EB, uni01EE, uni01EF, uni01F1, uni01F2, uni01F3, uni01F4, uni01F5, uni0200, uni0201, uni0202, uni0203, uni0204, uni0205, uni0206, uni0207, uni0208, uni0209, uni020A, uni020B, uni020C, uni020D, uni020E, uni020F, uni0210, uni0211, uni0212, uni0213, uni0214, uni0215, uni0216, uni0217, uni0218, uni0219, uni021A, uni021B, uni021E, uni021F, uni022A, uni022B, uni022C, uni022D, uni0230, uni0231, uni0232, uni0233, uni0237, uni0259, uni0292, uni02BC, uni02C9, uni0302, uni0302.case, uni03020300, uni03020301, uni03020303, uni03020309, uni0304, uni0306, uni03060300, uni03060301, uni03060303, uni03060309, uni0307, uni0308, uni030A, uni030B, uni030C, uni030C.alt, uni030F, uni0311, uni0312, uni031B, uni031B.case, uni0324, uni0326, uni0326.alt, uni0327, uni0328, uni032E, uni0331, uni0335, uni0400, uni0401, uni0402, uni0403, uni0404, uni0405, uni0406, uni0407, uni0408, uni0409, uni040A, uni040B, uni040C, uni040D, uni040E, uni040F, uni0410, uni0411, uni0412, uni0413, uni0414, uni0415, uni0416, uni0417, uni0418, uni0419, uni041A, uni041B, uni041C, uni041D, uni041E, uni041F, uni0420, uni0421, uni0422, uni0423, uni0424, uni0425, uni0426, uni0427, uni0428, uni0429, uni042A, uni042B, uni042C, uni042D, uni042E, uni042F, uni0430, uni0431, uni0432, uni0433, uni0434, uni0435, uni0436, uni0437, uni0438, uni0439, uni043A, uni043B, uni043C, uni043D, uni043E, uni043F, uni0440, uni0441, uni0442, uni0443, uni0444, uni0445, uni0446, uni0447, uni0448, uni0449, uni044A, uni044B, uni044C, uni044D, uni044E, uni044F, uni0450, uni0451, uni0452, uni0453, uni0454, uni0455, uni0456, uni0457, uni0458, uni0459, uni045A, uni045B, uni045C, uni045D, uni045E, uni045F, uni0462, uni0463, uni046A, uni046B, uni0490, uni0491, uni0492, uni0493, uni0496, uni0497, uni049A, uni049B, uni04A2, uni04A3, uni04BA, uni04BB, uni04C9, uni04CA, uni04D8, uni04D9, uni04E8, uni04E9, uni1E02, uni1E03, uni1E0A, uni1E0B, uni1E1E, uni1E1F, uni1E40, uni1E41, uni1E56, uni1E57, uni1E60, uni1E61, uni1E6A, uni1E6B, uni1E9E, uni1EA0, uni1EA1, uni1EA2, uni1EA3, uni1EA4, uni1EA5, uni1EA6, uni1EA7, uni1EA8, uni1EA9, uni1EAA, uni1EAB, uni1EAC, uni1EAD, uni1EAE, uni1EAF, uni1EB0, uni1EB1, uni1EB2, uni1EB3, uni1EB4, uni1EB5, uni1EB6, uni1EB7, uni1EB8, uni1EB9, uni1EBA, uni1EBB, uni1EBC, uni1EBD, uni1EBE, uni1EBF, uni1EC0, uni1EC1, uni1EC2, uni1EC3, uni1EC4, uni1EC5, uni1EC6, uni1EC7, uni1EC8, uni1EC9, uni1ECA, uni1ECB, uni1ECC, uni1ECD, uni1ECE, uni1ECF, uni1ED0, uni1ED1, uni1ED2, uni1ED3, uni1ED4, uni1ED5, uni1ED6, uni1ED7, uni1ED8, uni1ED9, uni1EDA, uni1EDB, uni1EDC, uni1EDD, uni1EDE, uni1EDF, uni1EE0, uni1EE1, uni1EE2, uni1EE3, uni1EE4, uni1EE5, uni1EE6, uni1EE7, uni1EE8, uni1EE9, uni1EEA, uni1EEB, uni1EEC, uni1EED, uni1EEE, uni1EEF, uni1EF0, uni1EF1, uni1EF4, uni1EF5, uni1EF6, uni1EF7, uni1EF8, uni1EF9, uni2010, uni2052, uni2074, uni20A6, uni20A9, uni20AD, uni20B1, uni20B2, uni20B5, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, uni212A, uni212B, uni2215, uni2219, uni27E8, uni27E9, uogonek, uring, ustraitcy, ustraitstrokecy, utilde, v, w, wacute, wcircumflex, wdieresis, wgrave, x, y, yacute, ycircumflex, ydieresis, yen, ygrave, z, zacute, zcaron, zdotaccent, zero]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* asterisk (U+002A): X=205.0,Y=809.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=162.0,Y=809.0 (should be at cap-height 810?)
	* at (U+0040): X=435.0,Y=809.0 (should be at cap-height 810?)
	* J (U+004A): X=8.0,Y=-2.0 (should be at baseline 0?)
	* Q (U+0051): X=333.0,Y=-1.0 (should be at baseline 0?)
	* IJ (U+0132): X=214.0,Y=-2.0 (should be at baseline 0?)
	* Jcircumflex (U+0134): X=8.0,Y=-2.0 (should be at baseline 0?)
	* uni01C7 (U+01C7): X=381.0,Y=-2.0 (should be at baseline 0?)
	* uni01CA (U+01CA): X=523.0,Y=-2.0 (should be at baseline 0?)
	* uni01E9 (U+01E9): X=210.0,Y=809.0 (should be at cap-height 810?) and 16 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* uni040E (U+040E): L<<241.0,173.0>--<179.0,436.0>> -> L<<179.0,436.0>--<87.0,810.0>>
	* uni040E (U+040E): L<<376.0,810.0>--<295.0,438.0>> -> L<<295.0,438.0>--<241.0,173.0>>
	* uni0423 (U+0423): L<<241.0,173.0>--<179.0,436.0>> -> L<<179.0,436.0>--<87.0,810.0>>
	* uni0423 (U+0423): L<<376.0,810.0>--<295.0,438.0>> -> L<<295.0,438.0>--<241.0,173.0>>
	* uni04EE (U+04EE): L<<241.0,173.0>--<179.0,436.0>> -> L<<179.0,436.0>--<87.0,810.0>>
	* uni04EE (U+04EE): L<<376.0,810.0>--<295.0,438.0>> -> L<<295.0,438.0>--<241.0,173.0>>
	* uni04F0 (U+04F0): L<<241.0,173.0>--<179.0,436.0>> -> L<<179.0,436.0>--<87.0,810.0>>
	* uni04F0 (U+04F0): L<<376.0,810.0>--<295.0,438.0>> -> L<<295.0,438.0>--<241.0,173.0>>
	* uni04F2 (U+04F2): L<<241.0,173.0>--<179.0,436.0>> -> L<<179.0,436.0>--<87.0,810.0>> and uni04F2 (U+04F2): L<<376.0,810.0>--<295.0,438.0>> -> L<<295.0,438.0>--<241.0,173.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * five (U+0035): L<<131.0,449.0>--<133.0,764.0>>
 * onequarter (U+00BC): L<<562.0,359.0>--<563.0,168.0>>
 * threequarters (U+00BE): L<<639.0,359.0>--<640.0,168.0>>
 * uni043C (U+043C): L<<375.0,443.0>--<377.0,0.0>>
 * uni043C (U+043C): L<<423.0,0.0>--<419.0,578.0>>
 * uni043C (U+043C): L<<57.0,578.0>--<52.0,0.0>>
 * uni043C (U+043C): L<<99.0,0.0>--<101.0,441.0>>
 * uni04CE (U+04CE): L<<375.0,443.0>--<377.0,0.0>>
 * uni04CE (U+04CE): L<<423.0,37.0>--<419.0,578.0>>
 * uni04CE (U+04CE): L<<57.0,578.0>--<52.0,0.0>>
 * uni04CE (U+04CE): L<<99.0,0.0>--<101.0,441.0>> and uni2074 (U+2074): L<<201.0,792.0>--<202.0,601.0>> [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[13] Oswald-Medium.otf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [.notdef, A, AE, AEacute, Aacute, Abreve, Acircumflex, Adieresis, Agrave, Amacron, Aogonek, Aring, Aringacute, Atilde, B, C, Cacute, Ccaron, Ccedilla, Ccircumflex, Cdotaccent, D, Dcaron, Dcroat, E, Eacute, Ebreve, Ecaron, Ecircumflex, Edieresis, Edotaccent, Egrave, Emacron, Eng, Eogonek, Eth, Euro, F, G, Gbreve, Gcaron, Gcircumflex, Gdotaccent, H, Hbar, Hcircumflex, I, IJ, Iacute, Ibreve, Icircumflex, Idieresis, Idotaccent, Igrave, Imacron, Iogonek, Itilde, J, Jcircumflex, K, L, Lacute, Lcaron, Ldot, Lslash, M, N, Nacute, Ncaron, Ntilde, O, OE, Oacute, Obreve, Ocircumflex, Odieresis, Ograve, Ohorn, Ohungarumlaut, Omacron, Oslash, Oslashacute, Otilde, P, Pi, Q, R, Racute, Rcaron, S, Sacute, Scaron, Scedilla, Scircumflex, T, Tbar, Tcaron, Thorn, U, Uacute, Ubreve, Ucircumflex, Udieresis, Ugrave, Uhorn, Uhungarumlaut, Umacron, Uogonek, Uring, Ustraitcy, Ustraitstrokecy, Utilde, V, W, Wacute, Wcircumflex, Wdieresis, Wgrave, X, Y, Yacute, Ycircumflex, Ydieresis, Ygrave, Z, Zacute, Zcaron, Zdotaccent, a, aacute, abreve, acircumflex, acute, acutecomb, adieresis, ae, aeacute, agrave, amacron, ampersand, aogonek, approxequal, aring, aringacute, asciicircum, asciitilde, asterisk, at, atilde, b, backslash, bar, braceleft, braceright, bracketleft, bracketright, breve, brokenbar, bullet, c, cacute, caron, ccaron, ccedilla, ccircumflex, cdotaccent, cedilla, cent, circumflex, colon, colonmonetary, comma, copyright, currency, d, dagger, daggerdbl, dcaron, dcroat, degree, dieresis, divide, dollar, dong, dotaccent, dotbelowcomb, dotlessi, e, eacute, ebreve, ecaron, ecircumflex, edieresis, edotaccent, egrave, eight, ellipsis, emacron, emdash, emptyset, endash, eng, eogonek, equal, estimated, eth, exclam, exclamdown, f, f_f, f_f_i, f_f_ij, f_f_l, f_ij, fi, five, fl, florin, four, fraction, franc, g, gbreve, gcaron, gcircumflex, gdotaccent, germandbls, grave, gravecomb, greater, greaterequal, guillemotleft, guillemotright, guilsinglleft, guilsinglright, h, hbar, hcircumflex, hookabovecomb, hungarumlaut, hyphen, i, i.loclTRK, iacute, ibreve, icircumflex, idieresis, igrave, ij, imacron, infinity, integral, iogonek, itilde, j, jcircumflex, k, kgreenlandic, l, lacute, lcaron, ldot, less, lessequal, lira, logicalnot, longs, lozenge, lslash, m, macron, minus, minute, multiply, n, nacute, napostrophe, ncaron, nine, notequal, ntilde, numbersign, o, oacute, obreve, ocircumflex, odieresis, oe, ogonek, ograve, ohorn, ohungarumlaut, omacron, one, onehalf, onequarter, ordfeminine, ordmasculine, oslash, oslashacute, otilde, p, paragraph, parenleft, parenright, partialdiff, percent, period, periodcentered, periodcentered.loclCAT, perthousand, peseta, pi, plus, plusminus, product, q, question, questiondown, quotedbl, quotedblbase, quotedblleft, quotedblright, quoteleft, quoteright, quotesinglbase, quotesingle, r, racute, radical, rcaron, registered, ring, s, sacute, scaron, scedilla, scircumflex, second, section, semicolon, seven, six, slash, sterling, summation, t, tbar, tcaron, thorn, three, threequarters, tilde, tildecomb, trademark, two, u, uacute, ubreve, ucircumflex, udieresis, ugrave, uhorn, uhungarumlaut, umacron, underscore, uni00AD, uni00B2, uni00B3, uni00B5, uni00B9, uni0122, uni0123, uni0136, uni0137, uni013B, uni013C, uni0145, uni0146, uni0156, uni0157, uni0162, uni0163, uni018F, uni01B7, uni01C4, uni01C5, uni01C6, uni01C7, uni01C8, uni01C9, uni01CA, uni01CB, uni01CC, uni01CD, uni01CE, uni01D3, uni01D4, uni01E4, uni01E5, uni01E8, uni01E9, uni01EA, uni01EB, uni01EE, uni01EF, uni01F1, uni01F2, uni01F3, uni01F4, uni01F5, uni0200, uni0201, uni0202, uni0203, uni0204, uni0205, uni0206, uni0207, uni0208, uni0209, uni020A, uni020B, uni020C, uni020D, uni020E, uni020F, uni0210, uni0211, uni0212, uni0213, uni0214, uni0215, uni0216, uni0217, uni0218, uni0219, uni021A, uni021B, uni021E, uni021F, uni022A, uni022B, uni022C, uni022D, uni0230, uni0231, uni0232, uni0233, uni0237, uni0259, uni0292, uni02BC, uni02C9, uni0302, uni0302.case, uni03020300, uni03020301, uni03020303, uni03020309, uni0304, uni0306, uni03060300, uni03060301, uni03060303, uni03060309, uni0307, uni0308, uni030A, uni030B, uni030C, uni030C.alt, uni030F, uni0311, uni0312, uni031B, uni031B.case, uni0324, uni0326, uni0326.alt, uni0327, uni0328, uni032E, uni0331, uni0335, uni0400, uni0401, uni0402, uni0403, uni0404, uni0405, uni0406, uni0407, uni0408, uni0409, uni040A, uni040B, uni040C, uni040D, uni040E, uni040F, uni0410, uni0411, uni0412, uni0413, uni0414, uni0415, uni0416, uni0417, uni0418, uni0419, uni041A, uni041B, uni041C, uni041D, uni041E, uni041F, uni0420, uni0421, uni0422, uni0423, uni0424, uni0425, uni0426, uni0427, uni0428, uni0429, uni042A, uni042B, uni042C, uni042D, uni042E, uni042F, uni0430, uni0431, uni0432, uni0433, uni0434, uni0435, uni0436, uni0437, uni0438, uni0439, uni043A, uni043B, uni043C, uni043D, uni043E, uni043F, uni0440, uni0441, uni0442, uni0443, uni0444, uni0445, uni0446, uni0447, uni0448, uni0449, uni044A, uni044B, uni044C, uni044D, uni044E, uni044F, uni0450, uni0451, uni0452, uni0453, uni0454, uni0455, uni0456, uni0457, uni0458, uni0459, uni045A, uni045B, uni045C, uni045D, uni045E, uni045F, uni0462, uni0463, uni046A, uni046B, uni0490, uni0491, uni0492, uni0493, uni0496, uni0497, uni049A, uni049B, uni04A2, uni04A3, uni04BA, uni04BB, uni04C9, uni04CA, uni04D8, uni04D9, uni04E8, uni04E9, uni1E02, uni1E03, uni1E0A, uni1E0B, uni1E1E, uni1E1F, uni1E40, uni1E41, uni1E56, uni1E57, uni1E60, uni1E61, uni1E6A, uni1E6B, uni1E9E, uni1EA0, uni1EA1, uni1EA2, uni1EA3, uni1EA4, uni1EA5, uni1EA6, uni1EA7, uni1EA8, uni1EA9, uni1EAA, uni1EAB, uni1EAC, uni1EAD, uni1EAE, uni1EAF, uni1EB0, uni1EB1, uni1EB2, uni1EB3, uni1EB4, uni1EB5, uni1EB6, uni1EB7, uni1EB8, uni1EB9, uni1EBA, uni1EBB, uni1EBC, uni1EBD, uni1EBE, uni1EBF, uni1EC0, uni1EC1, uni1EC2, uni1EC3, uni1EC4, uni1EC5, uni1EC6, uni1EC7, uni1EC8, uni1EC9, uni1ECA, uni1ECB, uni1ECC, uni1ECD, uni1ECE, uni1ECF, uni1ED0, uni1ED1, uni1ED2, uni1ED3, uni1ED4, uni1ED5, uni1ED6, uni1ED7, uni1ED8, uni1ED9, uni1EDA, uni1EDB, uni1EDC, uni1EDD, uni1EDE, uni1EDF, uni1EE0, uni1EE1, uni1EE2, uni1EE3, uni1EE4, uni1EE5, uni1EE6, uni1EE7, uni1EE8, uni1EE9, uni1EEA, uni1EEB, uni1EEC, uni1EED, uni1EEE, uni1EEF, uni1EF0, uni1EF1, uni1EF4, uni1EF5, uni1EF6, uni1EF7, uni1EF8, uni1EF9, uni2010, uni2052, uni2074, uni20A6, uni20A9, uni20AD, uni20B1, uni20B2, uni20B5, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, uni212A, uni212B, uni2215, uni2219, uni27E8, uni27E9, uogonek, uring, ustraitcy, ustraitstrokecy, utilde, v, w, wacute, wcircumflex, wdieresis, wgrave, x, y, yacute, ycircumflex, ydieresis, yen, ygrave, z, zacute, zcaron, zdotaccent, zero]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* exclam (U+0021): X=186.0,Y=809.0 (should be at cap-height 810?)
	* exclam (U+0021): X=50.0,Y=809.0 (should be at cap-height 810?)
	* percent (U+0025): X=639.0,Y=811.0 (should be at cap-height 810?)
	* percent (U+0025): X=548.0,Y=811.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=268.0,Y=809.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=166.0,Y=809.0 (should be at cap-height 810?)
	* W (U+0057): X=406.0,Y=808.0 (should be at cap-height 810?)
	* W (U+0057): X=306.0,Y=808.0 (should be at cap-height 810?)
	* k (U+006B): X=54.0,Y=1.0 (should be at baseline 0?)
	* k (U+006B): X=186.0,Y=1.0 (should be at baseline 0?) and 57 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are any segments inordinately short?</summary>

* [com.google.fonts/check/outline_short_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_short_segments)
<pre>--- Rationale ---
This check looks for outline segments which seem particularly short (less than
0.6% of the overall path length).
This check is not run for variable fonts, as they may legitimately have short
segments. As this check is liable to generate significant numbers of false
positives, it will pass if there are more than 100 reported short segments.</pre>

* ⚠ **WARN** The following glyphs have segments which seem very short:
	* six (U+0036) contains a short segment B<<469.0,603.0>-<469.0,608.0>-<469.0,613.0>-<469.0,616.0>>
	* nine (U+0039) contains a short segment L<<50.0,206.0>--<50.0,194.0>>
	* uni00B3 (U+00B3) contains a short segment L<<178.0,746.0>--<178.0,750.0>>
	* threequarters (U+00BE) contains a short segment L<<158.0,667.0>--<158.0,671.0>>
	* uni01E5 (U+01E5) contains a short segment B<<23.0,-58.0>-<23.0,-62.0>-<22.0,-66.0>-<22.0,-71.0>>
	* uni0402 (U+0402) contains a short segment B<<405.0,84.0>-<399.0,84.0>-<392.0,83.0>-<385.0,84.0>>
	* uni0416 (U+0416) contains a short segment L<<301.0,399.0>--<309.0,399.0>>
	* uni0416 (U+0416) contains a short segment L<<428.0,399.0>--<437.0,399.0>>
	* uni0416 (U+0416) contains a short segment L<<436.0,425.0>--<428.0,425.0>>
	* uni0416 (U+0416) contains a short segment L<<309.0,425.0>--<302.0,425.0>> and 45 more. [code: found-short-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* partialdiff (U+2202): L<<164.0,154.0>--<164.0,168.0>> -> L<<164.0,168.0>--<184.0,374.0>>
	* uni040E (U+040E): L<<264.0,235.0>--<227.0,471.0>> -> L<<227.0,471.0>--<158.0,810.0>>
	* uni040E (U+040E): L<<354.0,810.0>--<294.0,471.0>> -> L<<294.0,471.0>--<264.0,235.0>>
	* uni0423 (U+0423): L<<264.0,235.0>--<227.0,471.0>> -> L<<227.0,471.0>--<158.0,810.0>>
	* uni0423 (U+0423): L<<354.0,810.0>--<294.0,471.0>> -> L<<294.0,471.0>--<264.0,235.0>>
	* uni04EE (U+04EE): L<<264.0,235.0>--<227.0,471.0>> -> L<<227.0,471.0>--<158.0,810.0>>
	* uni04EE (U+04EE): L<<354.0,810.0>--<294.0,471.0>> -> L<<294.0,471.0>--<264.0,235.0>>
	* uni04F0 (U+04F0): L<<264.0,235.0>--<227.0,471.0>> -> L<<227.0,471.0>--<158.0,810.0>>
	* uni04F0 (U+04F0): L<<354.0,810.0>--<294.0,471.0>> -> L<<294.0,471.0>--<264.0,235.0>>
	* uni04F2 (U+04F2): L<<264.0,235.0>--<227.0,471.0>> -> L<<227.0,471.0>--<158.0,810.0>> and uni04F2 (U+04F2): L<<354.0,810.0>--<294.0,471.0>> -> L<<294.0,471.0>--<264.0,235.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---
This check heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed up
by manual inspection.</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* M (U+004D): L<<170.0,0.0>--<181.0,565.0>>/L<<181.0,565.0>--<298.0,0.0>> = 12.814780858650376
	* M (U+004D): L<<387.0,0.0>--<502.0,563.0>>/L<<502.0,563.0>--<514.0,0.0>> = 12.76562918981905
	* uni041C (U+041C): L<<170.0,0.0>--<181.0,565.0>>/L<<181.0,565.0>--<298.0,0.0>> = 12.814780858650376
	* uni041C (U+041C): L<<387.0,0.0>--<502.0,563.0>>/L<<502.0,563.0>--<514.0,0.0>> = 12.76562918981905
	* uni04CD (U+04CD): L<<170.0,0.0>--<181.0,565.0>>/L<<181.0,565.0>--<298.0,0.0>> = 12.814780858650376
	* uni04CD (U+04CD): L<<387.0,0.0>--<502.0,563.0>>/L<<502.0,563.0>--<514.0,0.0>> = 12.76562918981905
	* uni1E40 (U+1E40): L<<170.0,0.0>--<181.0,565.0>>/L<<181.0,565.0>--<298.0,0.0>> = 12.814780858650376 and uni1E40 (U+1E40): L<<387.0,0.0>--<502.0,563.0>>/L<<502.0,563.0>--<514.0,0.0>> = 12.76562918981905 [code: found-jaggy-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * bracketleft (U+005B): L<<174.0,-125.0>--<175.0,751.0>>
 * lira (U+20A4): L<<323.0,480.0>--<203.0,481.0>>
 * onequarter (U+00BC): L<<651.0,312.0>--<652.0,173.0>>
 * radical (U+221A): L<<11.0,494.0>--<127.0,495.0>>
 * threequarters (U+00BE): L<<713.0,312.0>--<714.0,173.0>>
 * uni0122 (U+0122): L<<345.0,-183.0>--<346.0,-66.0>>
 * uni0123 (U+0123): L<<171.0,759.0>--<170.0,642.0>>
 * uni0136 (U+0136): L<<332.0,-183.0>--<333.0,-66.0>>
 * uni013B (U+013B): L<<298.0,-183.0>--<299.0,-66.0>>
 * uni013C (U+013C): L<<194.0,-183.0>--<195.0,-66.0>> and 10 more. [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[12] Oswald-Light.otf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [.notdef, A, AE, AEacute, Aacute, Abreve, Acircumflex, Adieresis, Agrave, Amacron, Aogonek, Aring, Aringacute, Atilde, B, C, Cacute, Ccaron, Ccedilla, Ccircumflex, Cdotaccent, D, Dcaron, Dcroat, E, Eacute, Ebreve, Ecaron, Ecircumflex, Edieresis, Edotaccent, Egrave, Emacron, Eng, Eogonek, Eth, Euro, F, G, Gbreve, Gcaron, Gcircumflex, Gdotaccent, H, Hbar, Hcircumflex, I, IJ, Iacute, Ibreve, Icircumflex, Idieresis, Idotaccent, Igrave, Imacron, Iogonek, Itilde, J, Jcircumflex, K, L, Lacute, Lcaron, Ldot, Lslash, M, N, Nacute, Ncaron, Ntilde, O, OE, Oacute, Obreve, Ocircumflex, Odieresis, Ograve, Ohorn, Ohungarumlaut, Omacron, Oslash, Oslashacute, Otilde, P, Pi, Q, R, Racute, Rcaron, S, Sacute, Scaron, Scedilla, Scircumflex, T, Tbar, Tcaron, Thorn, U, Uacute, Ubreve, Ucircumflex, Udieresis, Ugrave, Uhorn, Uhungarumlaut, Umacron, Uogonek, Uring, Ustraitcy, Ustraitstrokecy, Utilde, V, W, Wacute, Wcircumflex, Wdieresis, Wgrave, X, Y, Yacute, Ycircumflex, Ydieresis, Ygrave, Z, Zacute, Zcaron, Zdotaccent, a, aacute, abreve, acircumflex, acute, acutecomb, adieresis, ae, aeacute, agrave, amacron, ampersand, aogonek, approxequal, aring, aringacute, asciicircum, asciitilde, asterisk, at, atilde, b, backslash, bar, braceleft, braceright, bracketleft, bracketright, breve, brokenbar, bullet, c, cacute, caron, ccaron, ccedilla, ccircumflex, cdotaccent, cedilla, cent, circumflex, colon, colonmonetary, comma, copyright, currency, d, dagger, daggerdbl, dcaron, dcroat, degree, dieresis, divide, dollar, dong, dotaccent, dotbelowcomb, dotlessi, e, eacute, ebreve, ecaron, ecircumflex, edieresis, edotaccent, egrave, eight, ellipsis, emacron, emdash, emptyset, endash, eng, eogonek, equal, estimated, eth, exclam, exclamdown, f, f_f, f_f_i, f_f_ij, f_f_l, f_ij, fi, five, fl, florin, four, fraction, franc, g, gbreve, gcaron, gcircumflex, gdotaccent, germandbls, grave, gravecomb, greater, greaterequal, guillemotleft, guillemotright, guilsinglleft, guilsinglright, h, hbar, hcircumflex, hookabovecomb, hungarumlaut, hyphen, i, i.loclTRK, iacute, ibreve, icircumflex, idieresis, igrave, ij, imacron, infinity, integral, iogonek, itilde, j, jcircumflex, k, kgreenlandic, l, lacute, lcaron, ldot, less, lessequal, lira, logicalnot, longs, lozenge, lslash, m, macron, minus, minute, multiply, n, nacute, napostrophe, ncaron, nine, notequal, ntilde, numbersign, o, oacute, obreve, ocircumflex, odieresis, oe, ogonek, ograve, ohorn, ohungarumlaut, omacron, one, onehalf, onequarter, ordfeminine, ordmasculine, oslash, oslashacute, otilde, p, paragraph, parenleft, parenright, partialdiff, percent, period, periodcentered, periodcentered.loclCAT, perthousand, peseta, pi, plus, plusminus, product, q, question, questiondown, quotedbl, quotedblbase, quotedblleft, quotedblright, quoteleft, quoteright, quotesinglbase, quotesingle, r, racute, radical, rcaron, registered, ring, s, sacute, scaron, scedilla, scircumflex, second, section, semicolon, seven, six, slash, sterling, summation, t, tbar, tcaron, thorn, three, threequarters, tilde, tildecomb, trademark, two, u, uacute, ubreve, ucircumflex, udieresis, ugrave, uhorn, uhungarumlaut, umacron, underscore, uni00AD, uni00B2, uni00B3, uni00B5, uni00B9, uni0122, uni0123, uni0136, uni0137, uni013B, uni013C, uni0145, uni0146, uni0156, uni0157, uni0162, uni0163, uni018F, uni01B7, uni01C4, uni01C5, uni01C6, uni01C7, uni01C8, uni01C9, uni01CA, uni01CB, uni01CC, uni01CD, uni01CE, uni01D3, uni01D4, uni01E4, uni01E5, uni01E8, uni01E9, uni01EA, uni01EB, uni01EE, uni01EF, uni01F1, uni01F2, uni01F3, uni01F4, uni01F5, uni0200, uni0201, uni0202, uni0203, uni0204, uni0205, uni0206, uni0207, uni0208, uni0209, uni020A, uni020B, uni020C, uni020D, uni020E, uni020F, uni0210, uni0211, uni0212, uni0213, uni0214, uni0215, uni0216, uni0217, uni0218, uni0219, uni021A, uni021B, uni021E, uni021F, uni022A, uni022B, uni022C, uni022D, uni0230, uni0231, uni0232, uni0233, uni0237, uni0259, uni0292, uni02BC, uni02C9, uni0302, uni0302.case, uni03020300, uni03020301, uni03020303, uni03020309, uni0304, uni0306, uni03060300, uni03060301, uni03060303, uni03060309, uni0307, uni0308, uni030A, uni030B, uni030C, uni030C.alt, uni030F, uni0311, uni0312, uni031B, uni031B.case, uni0324, uni0326, uni0326.alt, uni0327, uni0328, uni032E, uni0331, uni0335, uni0400, uni0401, uni0402, uni0403, uni0404, uni0405, uni0406, uni0407, uni0408, uni0409, uni040A, uni040B, uni040C, uni040D, uni040E, uni040F, uni0410, uni0411, uni0412, uni0413, uni0414, uni0415, uni0416, uni0417, uni0418, uni0419, uni041A, uni041B, uni041C, uni041D, uni041E, uni041F, uni0420, uni0421, uni0422, uni0423, uni0424, uni0425, uni0426, uni0427, uni0428, uni0429, uni042A, uni042B, uni042C, uni042D, uni042E, uni042F, uni0430, uni0431, uni0432, uni0433, uni0434, uni0435, uni0436, uni0437, uni0438, uni0439, uni043A, uni043B, uni043C, uni043D, uni043E, uni043F, uni0440, uni0441, uni0442, uni0443, uni0444, uni0445, uni0446, uni0447, uni0448, uni0449, uni044A, uni044B, uni044C, uni044D, uni044E, uni044F, uni0450, uni0451, uni0452, uni0453, uni0454, uni0455, uni0456, uni0457, uni0458, uni0459, uni045A, uni045B, uni045C, uni045D, uni045E, uni045F, uni0462, uni0463, uni046A, uni046B, uni0490, uni0491, uni0492, uni0493, uni0496, uni0497, uni049A, uni049B, uni04A2, uni04A3, uni04BA, uni04BB, uni04C9, uni04CA, uni04D8, uni04D9, uni04E8, uni04E9, uni1E02, uni1E03, uni1E0A, uni1E0B, uni1E1E, uni1E1F, uni1E40, uni1E41, uni1E56, uni1E57, uni1E60, uni1E61, uni1E6A, uni1E6B, uni1E9E, uni1EA0, uni1EA1, uni1EA2, uni1EA3, uni1EA4, uni1EA5, uni1EA6, uni1EA7, uni1EA8, uni1EA9, uni1EAA, uni1EAB, uni1EAC, uni1EAD, uni1EAE, uni1EAF, uni1EB0, uni1EB1, uni1EB2, uni1EB3, uni1EB4, uni1EB5, uni1EB6, uni1EB7, uni1EB8, uni1EB9, uni1EBA, uni1EBB, uni1EBC, uni1EBD, uni1EBE, uni1EBF, uni1EC0, uni1EC1, uni1EC2, uni1EC3, uni1EC4, uni1EC5, uni1EC6, uni1EC7, uni1EC8, uni1EC9, uni1ECA, uni1ECB, uni1ECC, uni1ECD, uni1ECE, uni1ECF, uni1ED0, uni1ED1, uni1ED2, uni1ED3, uni1ED4, uni1ED5, uni1ED6, uni1ED7, uni1ED8, uni1ED9, uni1EDA, uni1EDB, uni1EDC, uni1EDD, uni1EDE, uni1EDF, uni1EE0, uni1EE1, uni1EE2, uni1EE3, uni1EE4, uni1EE5, uni1EE6, uni1EE7, uni1EE8, uni1EE9, uni1EEA, uni1EEB, uni1EEC, uni1EED, uni1EEE, uni1EEF, uni1EF0, uni1EF1, uni1EF4, uni1EF5, uni1EF6, uni1EF7, uni1EF8, uni1EF9, uni2010, uni2052, uni2074, uni20A6, uni20A9, uni20AD, uni20B1, uni20B2, uni20B5, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, uni212A, uni212B, uni2215, uni2219, uni27E8, uni27E9, uogonek, uring, ustraitcy, ustraitstrokecy, utilde, v, w, wacute, wcircumflex, wdieresis, wgrave, x, y, yacute, ycircumflex, ydieresis, yen, ygrave, z, zacute, zcaron, zdotaccent, zero]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* asterisk (U+002A): X=223.0,Y=809.0 (should be at cap-height 810?)
	* asterisk (U+002A): X=166.0,Y=809.0 (should be at cap-height 810?)
	* at (U+0040): X=464.0,Y=809.0 (should be at cap-height 810?)
	* t (U+0074): X=255.0,Y=-1.0 (should be at baseline 0?)
	* questiondown (U+00BF): X=131.0,Y=1.0 (should be at baseline 0?)
	* uni0163 (U+0163): X=255.0,Y=-1.0 (should be at baseline 0?)
	* tcaron (U+0165): X=255.0,Y=-1.0 (should be at baseline 0?)
	* tbar (U+0167): X=255.0,Y=-1.0 (should be at baseline 0?)
	* uni01E9 (U+01E9): X=218.0,Y=812.0 (should be at cap-height 810?)
	* uni01E9 (U+01E9): X=282.0,Y=812.0 (should be at cap-height 810?) and 34 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are any segments inordinately short?</summary>

* [com.google.fonts/check/outline_short_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_short_segments)
<pre>--- Rationale ---
This check looks for outline segments which seem particularly short (less than
0.6% of the overall path length).
This check is not run for variable fonts, as they may legitimately have short
segments. As this check is liable to generate significant numbers of false
positives, it will pass if there are more than 100 reported short segments.</pre>

* ⚠ **WARN** The following glyphs have segments which seem very short:
	* two (U+0032) contains a short segment L<<128.0,570.0>--<128.0,588.0>>
	* three (U+0033) contains a short segment L<<129.0,604.0>--<129.0,618.0>>
	* three (U+0033) contains a short segment B<<215.0,392.0>-<217.0,392.0>-<233.0,392.0>-<235.0,392.0>>
	* three (U+0033) contains a short segment L<<58.0,207.0>--<58.0,187.0>>
	* six (U+0036) contains a short segment B<<435.0,614.0>-<435.0,616.0>-<434.0,629.0>-<434.0,631.0>>
	* nine (U+0039) contains a short segment L<<67.0,194.0>--<67.0,180.0>>
	* at (U+0040) contains a short segment L<<565.0,599.0>--<556.0,580.0>>
	* m (U+006D) contains a short segment B<<359.0,456.0>-<359.0,464.0>-<358.0,471.0>-<357.0,478.0>>
	* uni00B3 (U+00B3) contains a short segment L<<105.0,752.0>--<105.0,756.0>>
	* uni00B3 (U+00B3) contains a short segment L<<48.0,569.0>--<48.0,559.0>> and 79 more. [code: found-short-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* uni040E (U+040E): L<<239.0,186.0>--<185.0,447.0>> -> L<<185.0,447.0>--<102.0,810.0>>
	* uni040E (U+040E): L<<360.0,810.0>--<286.0,447.0>> -> L<<286.0,447.0>--<239.0,186.0>>
	* uni0423 (U+0423): L<<239.0,186.0>--<185.0,447.0>> -> L<<185.0,447.0>--<102.0,810.0>>
	* uni0423 (U+0423): L<<360.0,810.0>--<286.0,447.0>> -> L<<286.0,447.0>--<239.0,186.0>>
	* uni04EE (U+04EE): L<<239.0,186.0>--<185.0,447.0>> -> L<<185.0,447.0>--<102.0,810.0>>
	* uni04EE (U+04EE): L<<360.0,810.0>--<286.0,447.0>> -> L<<286.0,447.0>--<239.0,186.0>>
	* uni04F0 (U+04F0): L<<239.0,186.0>--<185.0,447.0>> -> L<<185.0,447.0>--<102.0,810.0>>
	* uni04F0 (U+04F0): L<<360.0,810.0>--<286.0,447.0>> -> L<<286.0,447.0>--<239.0,186.0>>
	* uni04F2 (U+04F2): L<<239.0,186.0>--<185.0,447.0>> -> L<<185.0,447.0>--<102.0,810.0>> and uni04F2 (U+04F2): L<<360.0,810.0>--<286.0,447.0>> -> L<<286.0,447.0>--<239.0,186.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * onequarter (U+00BC): L<<605.0,342.0>--<606.0,168.0>>
 * threequarters (U+00BE): L<<668.0,342.0>--<669.0,168.0>>
 * uni00B5 (U+00B5): L<<51.0,578.0>--<52.0,-173.0>>
 * uni01EB (U+01EB): L<<353.0,209.0>--<354.0,369.0>>
 * uni043C (U+043C): L<<115.0,0.0>--<116.0,404.0>>
 * uni043C (U+043C): L<<380.0,406.0>--<381.0,0.0>>
 * uni043C (U+043C): L<<444.0,0.0>--<439.0,578.0>>
 * uni043C (U+043C): L<<57.0,578.0>--<52.0,0.0>>
 * uni04CE (U+04CE): L<<115.0,0.0>--<116.0,404.0>>
 * uni04CE (U+04CE): L<<380.0,406.0>--<381.0,0.0>> and 3 more. [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[13] Oswald-Bold.otf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Glyphs are similiar to Google Fonts version?</summary>

* [com.google.fonts/check/production_glyphs_similarity](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/production_glyphs_similarity)

* ⚠ **WARN** Following glyphs differ greatly from Google Fonts version: [.notdef, A, AE, AEacute, Aacute, Abreve, Acircumflex, Adieresis, Agrave, Amacron, Aogonek, Aring, Aringacute, Atilde, B, C, Cacute, Ccaron, Ccedilla, Ccircumflex, Cdotaccent, D, Dcaron, Dcroat, E, Eacute, Ebreve, Ecaron, Ecircumflex, Edieresis, Edotaccent, Egrave, Emacron, Eng, Eogonek, Eth, Euro, F, G, Gbreve, Gcaron, Gcircumflex, Gdotaccent, H, Hbar, Hcircumflex, I, IJ, Iacute, Ibreve, Icircumflex, Idieresis, Idotaccent, Igrave, Imacron, Iogonek, Itilde, J, Jcircumflex, K, L, Lacute, Lcaron, Ldot, Lslash, M, N, Nacute, Ncaron, Ntilde, O, OE, Oacute, Obreve, Ocircumflex, Odieresis, Ograve, Ohorn, Ohungarumlaut, Omacron, Oslash, Oslashacute, Otilde, P, Pi, Q, R, Racute, Rcaron, S, Sacute, Scaron, Scedilla, Scircumflex, T, Tbar, Tcaron, Thorn, U, Uacute, Ubreve, Ucircumflex, Udieresis, Ugrave, Uhorn, Uhungarumlaut, Umacron, Uogonek, Uring, Ustraitcy, Ustraitstrokecy, Utilde, V, W, Wacute, Wcircumflex, Wdieresis, Wgrave, X, Y, Yacute, Ycircumflex, Ydieresis, Ygrave, Z, Zacute, Zcaron, Zdotaccent, a, aacute, abreve, acircumflex, acute, acutecomb, adieresis, ae, aeacute, agrave, amacron, ampersand, aogonek, approxequal, aring, aringacute, asciicircum, asciitilde, asterisk, at, atilde, b, backslash, bar, braceleft, braceright, bracketleft, bracketright, breve, brokenbar, bullet, c, cacute, caron, ccaron, ccedilla, ccircumflex, cdotaccent, cedilla, cent, circumflex, colon, colonmonetary, comma, copyright, currency, d, dagger, daggerdbl, dcaron, dcroat, degree, dieresis, divide, dollar, dong, dotaccent, dotbelowcomb, dotlessi, e, eacute, ebreve, ecaron, ecircumflex, edieresis, edotaccent, egrave, eight, ellipsis, emacron, emdash, emptyset, endash, eng, eogonek, equal, estimated, eth, exclam, exclamdown, f, f_f, f_f_i, f_f_ij, f_f_l, f_ij, fi, five, fl, florin, four, fraction, franc, g, gbreve, gcaron, gcircumflex, gdotaccent, germandbls, grave, gravecomb, greater, greaterequal, guillemotleft, guillemotright, guilsinglleft, guilsinglright, h, hbar, hcircumflex, hookabovecomb, hungarumlaut, hyphen, i, i.loclTRK, iacute, ibreve, icircumflex, idieresis, igrave, ij, imacron, infinity, integral, iogonek, itilde, j, jcircumflex, k, kgreenlandic, l, lacute, lcaron, ldot, less, lessequal, lira, logicalnot, longs, lozenge, lslash, m, macron, minus, minute, multiply, n, nacute, napostrophe, ncaron, nine, notequal, ntilde, numbersign, o, oacute, obreve, ocircumflex, odieresis, oe, ogonek, ograve, ohorn, ohungarumlaut, omacron, one, onehalf, onequarter, ordfeminine, ordmasculine, oslash, oslashacute, otilde, p, paragraph, parenleft, parenright, partialdiff, percent, period, periodcentered, periodcentered.loclCAT, perthousand, peseta, pi, plus, plusminus, product, q, question, questiondown, quotedbl, quotedblbase, quotedblleft, quotedblright, quoteleft, quoteright, quotesinglbase, quotesingle, r, racute, radical, rcaron, registered, ring, s, sacute, scaron, scedilla, scircumflex, second, section, semicolon, seven, six, slash, sterling, summation, t, tbar, tcaron, thorn, three, threequarters, tilde, tildecomb, trademark, two, u, uacute, ubreve, ucircumflex, udieresis, ugrave, uhorn, uhungarumlaut, umacron, underscore, uni00AD, uni00B2, uni00B3, uni00B5, uni00B9, uni0122, uni0123, uni0136, uni0137, uni013B, uni013C, uni0145, uni0146, uni0156, uni0157, uni0162, uni0163, uni018F, uni01B7, uni01C4, uni01C5, uni01C6, uni01C7, uni01C8, uni01C9, uni01CA, uni01CB, uni01CC, uni01CD, uni01CE, uni01D3, uni01D4, uni01E4, uni01E5, uni01E8, uni01E9, uni01EA, uni01EB, uni01EE, uni01EF, uni01F1, uni01F2, uni01F3, uni01F4, uni01F5, uni0200, uni0201, uni0202, uni0203, uni0204, uni0205, uni0206, uni0207, uni0208, uni0209, uni020A, uni020B, uni020C, uni020D, uni020E, uni020F, uni0210, uni0211, uni0212, uni0213, uni0214, uni0215, uni0216, uni0217, uni0218, uni0219, uni021A, uni021B, uni021E, uni021F, uni022A, uni022B, uni022C, uni022D, uni0230, uni0231, uni0232, uni0233, uni0237, uni0259, uni0292, uni02BC, uni02C9, uni0302, uni0302.case, uni03020300, uni03020301, uni03020303, uni03020309, uni0304, uni0306, uni03060300, uni03060301, uni03060303, uni03060309, uni0307, uni0308, uni030A, uni030B, uni030C, uni030C.alt, uni030F, uni0311, uni0312, uni031B, uni031B.case, uni0324, uni0326, uni0326.alt, uni0327, uni0328, uni032E, uni0331, uni0335, uni0400, uni0401, uni0402, uni0403, uni0404, uni0405, uni0406, uni0407, uni0408, uni0409, uni040A, uni040B, uni040C, uni040D, uni040E, uni040F, uni0410, uni0411, uni0412, uni0413, uni0414, uni0415, uni0416, uni0417, uni0418, uni0419, uni041A, uni041B, uni041C, uni041D, uni041E, uni041F, uni0420, uni0421, uni0422, uni0423, uni0424, uni0425, uni0426, uni0427, uni0428, uni0429, uni042A, uni042B, uni042C, uni042D, uni042E, uni042F, uni0430, uni0431, uni0432, uni0433, uni0434, uni0435, uni0436, uni0437, uni0438, uni0439, uni043A, uni043B, uni043C, uni043D, uni043E, uni043F, uni0440, uni0441, uni0442, uni0443, uni0444, uni0445, uni0446, uni0447, uni0448, uni0449, uni044A, uni044B, uni044C, uni044D, uni044E, uni044F, uni0450, uni0451, uni0452, uni0453, uni0454, uni0455, uni0456, uni0457, uni0458, uni0459, uni045A, uni045B, uni045C, uni045D, uni045E, uni045F, uni0462, uni0463, uni046A, uni046B, uni0490, uni0491, uni0492, uni0493, uni0496, uni0497, uni049A, uni049B, uni04A2, uni04A3, uni04BA, uni04BB, uni04C9, uni04CA, uni04D8, uni04D9, uni04E8, uni04E9, uni1E02, uni1E03, uni1E0A, uni1E0B, uni1E1E, uni1E1F, uni1E40, uni1E41, uni1E56, uni1E57, uni1E60, uni1E61, uni1E6A, uni1E6B, uni1E9E, uni1EA0, uni1EA1, uni1EA2, uni1EA3, uni1EA4, uni1EA5, uni1EA6, uni1EA7, uni1EA8, uni1EA9, uni1EAA, uni1EAB, uni1EAC, uni1EAD, uni1EAE, uni1EAF, uni1EB0, uni1EB1, uni1EB2, uni1EB3, uni1EB4, uni1EB5, uni1EB6, uni1EB7, uni1EB8, uni1EB9, uni1EBA, uni1EBB, uni1EBC, uni1EBD, uni1EBE, uni1EBF, uni1EC0, uni1EC1, uni1EC2, uni1EC3, uni1EC4, uni1EC5, uni1EC6, uni1EC7, uni1EC8, uni1EC9, uni1ECA, uni1ECB, uni1ECC, uni1ECD, uni1ECE, uni1ECF, uni1ED0, uni1ED1, uni1ED2, uni1ED3, uni1ED4, uni1ED5, uni1ED6, uni1ED7, uni1ED8, uni1ED9, uni1EDA, uni1EDB, uni1EDC, uni1EDD, uni1EDE, uni1EDF, uni1EE0, uni1EE1, uni1EE2, uni1EE3, uni1EE4, uni1EE5, uni1EE6, uni1EE7, uni1EE8, uni1EE9, uni1EEA, uni1EEB, uni1EEC, uni1EED, uni1EEE, uni1EEF, uni1EF0, uni1EF1, uni1EF4, uni1EF5, uni1EF6, uni1EF7, uni1EF8, uni1EF9, uni2010, uni2052, uni2074, uni20A6, uni20A9, uni20AD, uni20B1, uni20B2, uni20B5, uni20B9, uni20BA, uni20BC, uni20BD, uni2113, uni2116, uni212A, uni212B, uni2215, uni2219, uni27E8, uni27E9, uogonek, uring, ustraitcy, ustraitstrokecy, utilde, v, w, wacute, wcircumflex, wdieresis, wgrave, x, y, yacute, ycircumflex, ydieresis, yen, ygrave, z, zacute, zcaron, zdotaccent, zero]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there any misaligned on-curve points?</summary>

* [com.google.fonts/check/outline_alignment_miss](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_alignment_miss)
<pre>--- Rationale ---
This check heuristically looks for on-curve points which are close to, but do
not sit on, significant boundary coordinates. For example, a point which has a
Y-coordinate of 1 or -1 might be a misplaced baseline point. As well as the
baseline, here we also check for points near the x-height (but only for lower
case Latin letters), cap-height, ascender and descender Y coordinates.
Not all such misaligned curve points are a mistake, and sometimes the design may
call for points in locations near the boundaries. As this check is liable to
generate significant numbers of false positives, it will pass if there are more
than 100 reported misalignments.</pre>

* ⚠ **WARN** The following glyphs have on-curve points which have potentially incorrect y coordinates:
	* exclam (U+0021): X=211.0,Y=808.0 (should be at cap-height 810?)
	* exclam (U+0021): X=49.0,Y=808.0 (should be at cap-height 810?)
	* percent (U+0025): X=234.0,Y=811.0 (should be at cap-height 810?)
	* percent (U+0025): X=770.0,Y=-1.0 (should be at baseline 0?)
	* percent (U+0025): X=770.0,Y=-1.0 (should be at baseline 0?)
	* W (U+0057): X=407.0,Y=809.0 (should be at cap-height 810?)
	* W (U+0057): X=288.0,Y=809.0 (should be at cap-height 810?)
	* t (U+0074): X=330.0,Y=2.0 (should be at baseline 0?)
	* uni00B5 (U+00B5): X=205.0,Y=-1.0 (should be at baseline 0?)
	* Lcaron (U+013D): X=454.0,Y=811.0 (should be at cap-height 810?) and 66 more. [code: found-misalignments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are any segments inordinately short?</summary>

* [com.google.fonts/check/outline_short_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_short_segments)
<pre>--- Rationale ---
This check looks for outline segments which seem particularly short (less than
0.6% of the overall path length).
This check is not run for variable fonts, as they may legitimately have short
segments. As this check is liable to generate significant numbers of false
positives, it will pass if there are more than 100 reported short segments.</pre>

* ⚠ **WARN** The following glyphs have segments which seem very short:
	* six (U+0036) contains a short segment B<<482.0,599.0>-<482.0,603.0>-<481.0,608.0>-<481.0,613.0>>
	* nine (U+0039) contains a short segment L<<55.0,210.0>--<55.0,197.0>>
	* uni00B3 (U+00B3) contains a short segment L<<197.0,746.0>--<197.0,750.0>>
	* threequarters (U+00BE) contains a short segment L<<178.0,669.0>--<178.0,673.0>>
	* uni0402 (U+0402) contains a short segment B<<402.0,96.0>-<396.0,96.0>-<390.0,96.0>-<384.0,96.0>>
	* uni040C (U+040C) contains a short segment L<<242.0,353.0>--<260.0,353.0>>
	* uni040C (U+040C) contains a short segment L<<260.0,489.0>--<242.0,489.0>>
	* uni0416 (U+0416) contains a short segment L<<318.0,393.0>--<326.0,393.0>>
	* uni0416 (U+0416) contains a short segment L<<468.0,393.0>--<477.0,393.0>>
	* uni0416 (U+0416) contains a short segment L<<477.0,431.0>--<468.0,431.0>> and 52 more. [code: found-short-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do any segments have colinear vectors?</summary>

* [com.google.fonts/check/outline_colinear_vectors](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_colinear_vectors)
<pre>--- Rationale ---
This check looks for consecutive line segments which have the same angle. This
normally happens if an outline point has been added by accident.
This check is not run for variable fonts, as they may legitimately have colinear
vectors.</pre>

* ⚠ **WARN** The following glyphs have colinear vectors:
	* partialdiff (U+2202): L<<192.0,142.0>--<192.0,150.0>> -> L<<192.0,150.0>--<215.0,385.0>>
	* uni040E (U+040E): L<<291.0,260.0>--<258.0,477.0>> -> L<<258.0,477.0>--<188.0,810.0>>
	* uni040E (U+040E): L<<374.0,810.0>--<315.0,478.0>> -> L<<315.0,478.0>--<291.0,260.0>>
	* uni0423 (U+0423): L<<291.0,260.0>--<258.0,477.0>> -> L<<258.0,477.0>--<188.0,810.0>>
	* uni0423 (U+0423): L<<374.0,810.0>--<315.0,478.0>> -> L<<315.0,478.0>--<291.0,260.0>>
	* uni04EE (U+04EE): L<<291.0,260.0>--<258.0,477.0>> -> L<<258.0,477.0>--<188.0,810.0>>
	* uni04EE (U+04EE): L<<374.0,810.0>--<315.0,478.0>> -> L<<315.0,478.0>--<291.0,260.0>>
	* uni04F0 (U+04F0): L<<291.0,260.0>--<258.0,477.0>> -> L<<258.0,477.0>--<188.0,810.0>>
	* uni04F0 (U+04F0): L<<374.0,810.0>--<315.0,478.0>> -> L<<315.0,478.0>--<291.0,260.0>>
	* uni04F2 (U+04F2): L<<291.0,260.0>--<258.0,477.0>> -> L<<258.0,477.0>--<188.0,810.0>> and uni04F2 (U+04F2): L<<374.0,810.0>--<315.0,478.0>> -> L<<315.0,478.0>--<291.0,260.0>> [code: found-colinear-vectors]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any jaggy segments?</summary>

* [com.google.fonts/check/outline_jaggy_segments](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_jaggy_segments)
<pre>--- Rationale ---
This check heuristically detects outline segments which form a particularly
small angle, indicative of an outline error. This may cause false positives in
cases such as extreme ink traps, so should be regarded as advisory and backed up
by manual inspection.</pre>

* ⚠ **WARN** The following glyphs have jaggy segments:
	* M (U+004D): L<<186.0,0.0>--<198.0,543.0>>/L<<198.0,543.0>--<298.0,0.0>> = 11.700788695776914
	* M (U+004D): L<<411.0,0.0>--<505.0,539.0>>/L<<505.0,539.0>--<520.0,0.0>> = 11.486811882048746
	* W (U+0057): L<<288.0,809.0>--<227.0,338.0>>/L<<227.0,338.0>--<179.0,810.0>> = 13.186123471679563
	* W (U+0057): L<<520.0,810.0>--<471.0,341.0>>/L<<471.0,341.0>--<407.0,809.0>> = 13.751505055885582
	* Wacute (U+1E82): L<<288.0,809.0>--<227.0,338.0>>/L<<227.0,338.0>--<179.0,810.0>> = 13.186123471679563
	* Wacute (U+1E82): L<<520.0,810.0>--<471.0,341.0>>/L<<471.0,341.0>--<407.0,809.0>> = 13.751505055885582
	* Wcircumflex (U+0174): L<<288.0,809.0>--<227.0,338.0>>/L<<227.0,338.0>--<179.0,810.0>> = 13.186123471679563
	* Wcircumflex (U+0174): L<<520.0,810.0>--<471.0,341.0>>/L<<471.0,341.0>--<407.0,809.0>> = 13.751505055885582
	* Wdieresis (U+1E84): L<<288.0,809.0>--<227.0,338.0>>/L<<227.0,338.0>--<179.0,810.0>> = 13.186123471679563
	* Wdieresis (U+1E84): L<<520.0,810.0>--<471.0,341.0>>/L<<471.0,341.0>--<407.0,809.0>> = 13.751505055885582 and 15 more. [code: found-jaggy-segments]

</details>
<details>
<summary>⚠ <b>WARN:</b> Do outlines contain any semi-vertical or semi-horizontal lines?</summary>

* [com.google.fonts/check/outline_semi_vertical](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/<Section: Outline Correctness Checks>.html#com.google.fonts/check/outline_semi_vertical)
<pre>--- Rationale ---
This check detects line segments which are nearly, but not quite, exactly
horizontal or vertical. Sometimes such lines are created by design, but often
they are indicative of a design error.
This check is disabled for italic styles, which often contain nearly-upright
lines.</pre>

* ⚠ **WARN** The following glyphs have semi-vertical/semi-horizontal lines:
 * Uogonek (U+0172): L<<533.0,251.0>--<534.0,810.0>>
 * bar (U+007C): L<<65.0,810.0>--<64.0,-180.0>>
 * bracketleft (U+005B): L<<52.0,810.0>--<51.0,-185.0>>
 * bracketright (U+005D): L<<144.0,747.0>--<145.0,-122.0>>
 * bracketright (U+005D): L<<273.0,-185.0>--<272.0,810.0>>
 * lira (U+20A4): L<<357.0,486.0>--<238.0,487.0>>
 * onequarter (U+00BC): L<<627.0,310.0>--<628.0,177.0>>
 * threequarters (U+00BE): L<<708.0,310.0>--<709.0,177.0>>
 * uni00B5 (U+00B5): L<<41.0,578.0>--<42.0,-187.0>>
 * uni0122 (U+0122): L<<367.0,-199.0>--<368.0,-69.0>> and 22 more. [code: found-semi-vertical]

</details>
<br>
</details>
<details>
<summary><b>[7] Oswald[wght].ttf</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---
Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is stored
in the achVendID field of the OS/2 table.
Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:
https://docs.microsoft.com/en-us/typography/vendors/
This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.
Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.</pre>

* ⚠ **WARN** OS/2 VendorID value 'newt' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check copyright namerecords match license file.</summary>

* [com.google.fonts/check/name/license](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license)
<pre>--- Rationale ---
A known licensing description must be provided in the NameID 14 (LICENSE
DESCRIPTION) entries of the name table.
The source of truth for this check (to determine which license is in use) is a
file placed side-by-side to your font project including the licensing terms.
Depending on the chosen license, one of the following string snippets is
expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name
table:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> License URL matches License text on name table?</summary>

* [com.google.fonts/check/name/license_url](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/name/license_url)
<pre>--- Rationale ---
A known license URL must be provided in the NameID 14 (LICENSE INFO URL) entry
of the name table.
The source of truth for this check is the licensing text found on the NameID 13
entry (LICENSE DESCRIPTION).
The string snippets used for detecting licensing terms are:
- &quot;This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is available with a FAQ at: https://scripts.sil.org/OFL&quot;
- &quot;Licensed under the Apache License, Version 2.0&quot;
- &quot;Licensed under the Ubuntu Font Licence 1.0.&quot;
Currently accepted licenses are Apache or Open Font License.
For a small set of legacy families the Ubuntu Font License may be acceptable as
well.
When in doubt, please choose OFL for new font projects.</pre>

* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=13] [code: http-in-description]
* ⚠ **WARN** Please consider using HTTPS URLs at name table entry [plat=3, enc=1, name=14] [code: http-in-license-info]
* ⚠ **WARN** For now we're still accepting http URLs, but you should consider using https instead.
 [code: http]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---
All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.
If using GlyphsApp or UFOs, ligature carets can be defined as anchors with names
starting with &#x27;caret_&#x27;. These can be compiled with fontmake as of version
v2.4.0.</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Is there kerning info for non-ligated sequences?</summary>

* [com.google.fonts/check/kerning_for_non_ligated_sequences](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/kerning_for_non_ligated_sequences)
<pre>--- Rationale ---
Fonts with ligatures should have kerning on the corresponding non-ligated
sequences for text where ligatures aren&#x27;t used (eg
https://github.com/impallari/Raleway/issues/14).</pre>

* ⚠ **WARN** GPOS table lacks kerning info for the following non-ligated sequences:
	- f + f
	- f + i
	- i + f
	- f + l
	- l + f
	- i + l

   [code: lacks-kern-info]

</details>
<details>
<summary>⚠ <b>WARN:</b> Ensure fonts have ScriptLangTags declared on the 'meta' table.</summary>

* [com.google.fonts/check/meta/script_lang_tags](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/meta/script_lang_tags)
<pre>--- Rationale ---
The OpenType &#x27;meta&#x27; table originated at Apple. Microsoft added it to OT with
just two DataMap records:
- dlng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font is designed for
- slng: comma-separated ScriptLangTags that indicate which scripts, or languages
and scripts, with possible variants, the font supports
The slng structure is intended to describe which languages and scripts the font
overall supports. For example, a Traditional Chinese font that also contains
Latin characters, can indicate Hant,Latn, showing that it supports Hant, the
Traditional Chinese variant of the Hani script, and it also supports the Latn
script
The dlng structure is far more interesting. A font may contain various glyphs,
but only a particular subset of the glyphs may be truly &quot;leading&quot; in the design,
while other glyphs may have been included for technical reasons. Such a
Traditional Chinese font could only list Hant there, showing that it’s designed
for Traditional Chinese, but the font would omit Latn, because the developers
don’t think the font is really recommended for purely Latin-script use.
The tags used in the structures can comprise just script, or also language and
script. For example, if a font has Bulgarian Cyrillic alternates in the locl
feature for the cyrl BGR OT languagesystem, it could also indicate in dlng
explicitly that it supports bul-Cyrl. (Note that the scripts and languages in
meta use the ISO language and script codes, not the OpenType ones).
This check ensures that the font has the meta table containing the slng and dlng
structures.
All families in the Google Fonts collection should contain the &#x27;meta&#x27; table.
Windows 10 already uses it when deciding on which fonts to fall back to. The
Google Fonts API and also other environments could use the data for smarter
filtering. Most importantly, those entries should be added to the Noto fonts.
In the font making process, some environments store this data in external files
already. But the meta table provides a convenient way to store this inside the
font file, so some tools may add the data, and unrelated tools may read this
data. This makes the solution much more portable and universal.</pre>

* ⚠ **WARN** This font file does not have a 'meta' table. [code: lacks-meta-table]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does the font have a DSIG table?</summary>

* [com.google.fonts/check/dsig](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/dsig.html#com.google.fonts/check/dsig)
<pre>--- Rationale ---
Microsoft Office 2013 and below products expect fonts to have a digital
signature declared in a DSIG table in order to implement OpenType features. The
EOL date for Microsoft Office 2013 products is 4/11/2023. This issue does not
impact Microsoft Office 2016 and above products.
As we approach the EOL date, it is now considered better to completely remove
the table.
But if you still want your font to support OpenType features on Office 2013,
then you may find it handy to add a fake signature on a dummy DSIG table by
running one of the helper scripts provided at
https://github.com/googlefonts/gftools
Reference: https://github.com/googlefonts/fontbakery/issues/1845</pre>

* ⚠ **WARN** This font has a digital signature (DSIG table) which is only required - even if only a dummy placeholder - on old programs like MS Office 2013 in order to work properly.
The current recommendation is to completely remove the DSIG table. [code: found-DSIG]

</details>
<br>
</details>

### Summary

| 💔 ERROR | 🔥 FAIL | ⚠ WARN | 💤 SKIP | ℹ INFO | 🍞 PASS | 🔎 DEBUG |
|:-----:|:----:|:----:|:----:|:----:|:----:|:----:|
| 0 | 4 | 163 | 1352 | 81 | 1042 | 0 |
| 0% | 0% | 6% | 51% | 3% | 39% | 0% |

**Note:** The following loglevels were omitted in this report:
* **SKIP**
* **INFO**
* **PASS**
* **DEBUG**
