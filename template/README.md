SVG colour-scheme tests
=======================
This document illustrates how the icon template appears for users depending on their system's appearance settings ([dark mode] versus light mode, the assumed default).


Using [SVG views]
-----------------
<table>
	<thead>
		<tr>
			<th align="center">Result</th>
			<th align="center">SVG view</th>
			<th align="left">Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td align="center"><img src="icon.svg" height="32" alt="Icon (default)"/></td>
			<td align="center"><a name="default">None</a></td>
			<td>Default SVG display mode on GitHub</td>
		</tr>
		<tr>
			<td align="center"><img src="icon.svg#auto" height="32" alt="Icon (#auto)"/></td>
			<td align="center"><a name="auto"><code>#auto</code></a></td>
			<td>Automatic colour-theme selection</td>
		</tr>
		<tr>
			<td align="center"><img src="icon.svg#dark" height="32" alt="Icon (#dark)"/></td>
			<td align="center"><a name="dark"><code>#dark</code></a></td>
			<td>Dark-mode display (white-coloured shapes)</td>
		</tr>
		<tr>
			<td align="center"><img src="icon.svg#light" width="32" alt="Icon (#light)"/></td>
			<td align="center"><a name="light"><code>#light</code></a></td>
			<td>Light-mode display (black-coloured shapes)</td>
		</tr>
	</tbody>
</table>


Using [`<picture>`] elements
----------------------------
This example demonstrates the use of an HTML `<picture>` element to alternate between the icon's [`#dark`] and default views.
<table><thead><tr><th>Preview</th><th align="left">Source code</th></tr></thead><tbody><tr><td width="32" align="center" valign="middle">

<a href="icon.svg?raw=1"><picture>
	<source srcset="icon.svg#dark" height="70" media="(prefers-color-scheme: dark)"/>
	<img src="icon.svg" height="70" alt="&#xE000;"/>
</picture></a>

</td><td width="600" valign="middle">

```html
<a href="icon.svg?raw=1"><picture>
	<source srcset="icon.svg#dark" height="32" media="(prefers-color-scheme: dark)"/>
	<img src="icon.svg" height="32" alt="&#xE000;"/>
</picture></a>
```
</td></tr></tbody></table>

Note that this approach shouldn't be necessary if the icon's [`#auto`] view works as intended on GitHub (selecting the most appropriate colour-scheme based on the user's settings).


<!-- Referenced links -->
[dark mode]:   https://en.wikipedia.org/wiki/Dark_mode
[SVG views]:   https://developer.mozilla.org/en-US/docs/Web/SVG/Reference/Element/view
[`<picture>`]: https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/picture
[`#auto`]:     icon.svg?raw=1#auto
[`#dark`]:     icon.svg?raw=1#dark
[`#light`]:    icon.svg?raw=1#light
