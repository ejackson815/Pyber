# Pyber
What does the Data Represent?
From the data we can see that there fares, frequency, and usage time is larger in the suburbs than those in the city and rural areas.  This is attributed due to the population of people living in the specific areas as well as distance.  In the city its safe to say with public transportation and less space, average fares will be the lowest.  Suburbs has more of a population and has more of a demand.<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<title>PyUber Code & Plots</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>

<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    color: #000 !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.2.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.2.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.2.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.2.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.2.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.2.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=1);
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2);
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=3);
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1);
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1);
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
@media (max-width: 991px) {
  #ipython_notebook {
    margin-left: 10px;
  }
}
[dir="rtl"] #ipython_notebook {
  float: right !important;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#login_widget {
  float: right;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  text-align: center;
  vertical-align: middle;
  display: inline;
  opacity: 0;
  z-index: 2;
  width: 12ex;
  margin-right: -12ex;
}
.alternate_upload .btn-upload {
  height: 22px;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
[dir="rtl"] #tabs li {
  float: right;
}
ul#tabs {
  margin-bottom: 4px;
}
[dir="rtl"] ul#tabs {
  margin-right: 0px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons {
  float: left !important;
}
[dir="rtl"] .list_toolbar .pull-right {
  padding-top: 1px;
  float: left !important;
}
[dir="rtl"] .list_toolbar .pull-left {
  float: right !important;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: baseline;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
#tree-selector {
  padding-right: 0px;
}
[dir="rtl"] #tree-selector a {
  float: right;
}
#button-select-all {
  min-width: 50px;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
[dir="rtl"] #new-menu {
  text-align: right;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
[dir="rtl"] #running .col-sm-8 {
  float: right !important;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI colors. */
.ansibold {
  font-weight: bold;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  border-left-width: 1px;
  padding-left: 5px;
  background: linear-gradient(to right, transparent -40px, transparent 1px, transparent 1px, transparent 100%);
}
div.cell.jupyter-soft-selected {
  border-left-color: #90CAF9;
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected {
  border-color: #ababab;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 5px, transparent 5px, transparent 100%);
}
@media print {
  div.cell.selected {
    border-color: transparent;
  }
}
div.cell.selected.jupyter-soft-selected {
  border-left-width: 0;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 7px, #E3F2FD 7px, #E3F2FD 100%);
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #66BB6A -40px, #66BB6A 5px, transparent 5px, transparent 100%);
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  padding: 0.4em;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. We need the 0 value because of how we size */
  /* .CodeMirror-lines */
  padding: 0;
  border: 0;
  border-radius: 0;
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul {
  list-style: disc;
  margin: 0em 2em;
  padding-left: 0px;
}
.rendered_html ul ul {
  list-style: square;
  margin: 0em 2em;
}
.rendered_html ul ul ul {
  list-style: circle;
  margin: 0em 2em;
}
.rendered_html ol {
  list-style: decimal;
  margin: 0em 2em;
  padding-left: 0px;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin: 0em 2em;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
  margin: 0em 2em;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
  margin: 0em 2em;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
  margin: 0em 2em;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  background-color: #fff;
  color: #000;
  font-size: 100%;
  padding: 0px;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: 1px solid black;
  border-collapse: collapse;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  border: 1px solid black;
  border-collapse: collapse;
  margin: 1em 2em;
}
.rendered_html td,
.rendered_html th {
  text-align: left;
  vertical-align: middle;
  padding: 4px;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget {
  float: right !important;
  float: right;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  margin-top: 6px;
}
span.save_widget span.filename {
  height: 1em;
  line-height: 1em;
  padding: 3px;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  display: none;
}
.command-shortcut:before {
  content: "(command)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[92]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[93]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Read CSV</span>
<span class="n">city_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s2">&quot;city_data.csv&quot;</span><span class="p">)</span>
<span class="n">ride_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s2">&quot;ride_data.csv&quot;</span><span class="p">)</span>

<span class="c1">#city_data</span>

<span class="c1">#ride_data</span>

<span class="c1">#Merge City and Ride Data together on City</span>
<span class="n">ridesharedf</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">merge</span><span class="p">(</span><span class="n">city_data</span><span class="p">,</span> <span class="n">ride_data</span><span class="p">,</span> <span class="n">on</span><span class="o">=</span><span class="s2">&quot;city&quot;</span><span class="p">)</span>
<span class="n">ridesharedf</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt output_prompt">Out[93]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>city</th>
      <th>driver_count</th>
      <th>type</th>
      <th>date</th>
      <th>fare</th>
      <th>ride_id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Kelseyland</td>
      <td>63</td>
      <td>Urban</td>
      <td>8/19/2016 4:27</td>
      <td>5.51</td>
      <td>6.246010e+12</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Kelseyland</td>
      <td>63</td>
      <td>Urban</td>
      <td>4/17/2016 6:59</td>
      <td>5.54</td>
      <td>7.466470e+12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kelseyland</td>
      <td>63</td>
      <td>Urban</td>
      <td>5/4/2016 15:06</td>
      <td>30.54</td>
      <td>2.140500e+12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Kelseyland</td>
      <td>63</td>
      <td>Urban</td>
      <td>1/25/2016 20:44</td>
      <td>12.08</td>
      <td>1.896990e+12</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Kelseyland</td>
      <td>63</td>
      <td>Urban</td>
      <td>8/9/2016 18:19</td>
      <td>17.91</td>
      <td>8.784210e+12</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[94]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Bubble Plot</span>
<span class="c1">#Seperate Data Frames for Bubble Plot</span>
<span class="n">urban</span> <span class="o">=</span> <span class="n">ridesharedf</span><span class="o">.</span><span class="n">loc</span><span class="p">[(</span><span class="n">ridesharedf</span><span class="p">[</span><span class="s2">&quot;type&quot;</span><span class="p">]</span><span class="o">==</span><span class="s2">&quot;Urban&quot;</span><span class="p">)]</span>
<span class="n">rural</span> <span class="o">=</span> <span class="n">ridesharedf</span><span class="o">.</span><span class="n">loc</span><span class="p">[(</span><span class="n">ridesharedf</span><span class="p">[</span><span class="s2">&quot;type&quot;</span><span class="p">]</span><span class="o">==</span><span class="s2">&quot;Rural&quot;</span><span class="p">)]</span>
<span class="n">sub</span> <span class="o">=</span> <span class="n">ridesharedf</span><span class="o">.</span><span class="n">loc</span><span class="p">[(</span><span class="n">ridesharedf</span><span class="p">[</span><span class="s2">&quot;type&quot;</span><span class="p">]</span><span class="o">==</span><span class="s2">&quot;Suburban&quot;</span><span class="p">)]</span>

<span class="c1">#Average Fair Calculation per area</span>
<span class="n">avg_urban</span> <span class="o">=</span> <span class="n">urban</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])[</span><span class="s1">&#39;fare&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
<span class="c1">#avg_urban - checked to see if data populated</span>
<span class="n">avg_rural</span> <span class="o">=</span> <span class="n">rural</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])[</span><span class="s1">&#39;fare&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>
<span class="n">avg_sub</span> <span class="o">=</span> <span class="n">sub</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])[</span><span class="s1">&#39;fare&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>

<span class="c1">#Total Ride Calculation per area</span>
<span class="n">tride_urban</span> <span class="o">=</span> <span class="n">urban</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">count</span><span class="p">()[</span><span class="s1">&#39;ride_id&#39;</span><span class="p">]</span>
<span class="c1">#tride_urban</span>
<span class="n">tride_rural</span> <span class="o">=</span> <span class="n">rural</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">count</span><span class="p">()[</span><span class="s1">&#39;ride_id&#39;</span><span class="p">]</span>
<span class="n">tride_sub</span> <span class="o">=</span> <span class="n">sub</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">count</span><span class="p">()[</span><span class="s1">&#39;ride_id&#39;</span><span class="p">]</span>

<span class="c1">#Total drivers per area</span>
<span class="n">tdrivers_urban</span> <span class="o">=</span> <span class="n">urban</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])[</span><span class="s1">&#39;driver_count&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
<span class="c1">#tdrivers_urban</span>
<span class="n">tdrivers_rural</span> <span class="o">=</span> <span class="n">rural</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])[</span><span class="s1">&#39;driver_count&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
<span class="n">tdrivers_sub</span> <span class="o">=</span> <span class="n">sub</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;city&#39;</span><span class="p">])[</span><span class="s1">&#39;driver_count&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[95]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#test to check data for 1 of 3 data frames</span>
<span class="c1">#urban_df = pd.DataFrame({&quot;Average Fare&quot; : avg_urban, &quot;Total Rides&quot;:tride_urban, &quot;Total Drivers&quot;:tdrivers_urban})</span>
<span class="c1">#urban_df[&quot;Average Fare&quot;] = urban_df[&quot;Average Fare&quot;].map(&quot;{:,}&quot;.format)</span>
<span class="c1">#urban_df[&quot;Total Rides&quot;] =urban_df[&quot;Total Rides&quot;].map(&quot;{:,}&quot;.format)</span>
<span class="c1">#urban_df[&quot;Total Drivers&quot;] =urban_df[&quot;Total Drivers&quot;].map(&quot;{:,}&quot;.format)</span>
<span class="c1">#urban_df = urban_df.loc[:,[&quot;Average Fare&quot;, &quot;Total Rides&quot;, &quot;Total Drivers&quot;]]</span>
<span class="c1">#urban_df.sort_values(&quot;Average Fare&quot;, ascending =False).head()</span>

<span class="c1">#received type error - expecting tuplet received string..tried .format but still received the same error</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[96]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Creating Scatter Plot</span>
<span class="c1">#Urban</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">tride_urban</span><span class="p">,</span><span class="n">avg_urban</span><span class="p">,</span><span class="n">tdrivers_urban</span><span class="p">,</span> <span class="n">marker</span> <span class="o">=</span><span class="s1">&#39;+&#39;</span><span class="p">,</span> <span class="n">facecolors</span><span class="o">=</span> <span class="s2">&quot;purple&quot;</span><span class="p">,</span> <span class="n">alpha</span> <span class="o">=</span> <span class="o">.</span><span class="mi">44</span><span class="p">,</span> <span class="n">label</span> <span class="o">=</span> <span class="s2">&quot;Urban&quot;</span><span class="p">)</span>
<span class="c1">#Rural</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">tride_rural</span><span class="p">,</span><span class="n">avg_rural</span><span class="p">,</span><span class="n">tdrivers_rural</span><span class="p">,</span> <span class="n">marker</span> <span class="o">=</span><span class="s1">&#39;o&#39;</span><span class="p">,</span> <span class="n">facecolors</span> <span class="o">=</span> <span class="s2">&quot;yellow&quot;</span><span class="p">,</span> <span class="n">alpha</span> <span class="o">=</span> <span class="o">.</span><span class="mi">5</span><span class="p">,</span> <span class="n">label</span> <span class="o">=</span> <span class="s2">&quot;Rural&quot;</span><span class="p">)</span>
<span class="c1">#Suburbs</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">tride_sub</span><span class="p">,</span><span class="n">avg_sub</span><span class="p">,</span><span class="n">tdrivers_sub</span><span class="p">,</span> <span class="n">marker</span> <span class="o">=</span><span class="s1">&#39;*&#39;</span><span class="p">,</span> <span class="n">facecolors</span> <span class="o">=</span> <span class="s2">&quot;red&quot;</span><span class="p">,</span> <span class="n">alpha</span> <span class="o">=</span> <span class="o">.</span><span class="mi">54</span><span class="p">,</span> <span class="n">label</span> <span class="o">=</span> <span class="s2">&quot;Suburbs&quot;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt output_prompt">Out[96]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.collections.PathCollection at 0x1e9f80f20b8&gt;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[97]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#chart labels</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;PyUber Ride Sharing Data (2016)&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;Total Number of Rides (Per City)&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;Average Fare($)&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">(</span><span class="n">loc</span><span class="o">=</span> <span class="s1">&#39;lower right&#39;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt output_prompt">Out[97]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.legend.Legend at 0x1e9f81d25c0&gt;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[98]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">grid</span><span class="p">(</span><span class="n">b</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">which</span><span class="o">=</span><span class="s1">&#39;major&#39;</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;blue&#39;</span><span class="p">,</span> <span class="n">linestyle</span><span class="o">=</span><span class="s1">&#39;-&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s2">&quot;Pyber Scat Plt&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAYIAAAEWCAYAAABrDZDcAAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDIuMS4wLCBo
dHRwOi8vbWF0cGxvdGxpYi5vcmcvpW3flQAAIABJREFUeJzt3XeYVOXZx/Hvj6UsvSvg0kREirrq
WhAb1kSxJdYkxt41JmpssWt8bVFjTbAbTTSS2DUWIqgRUVCUsgiiqIsgvXe43z+eszAMs7tnd2d2
dnfuz3XNtTNnzjlzz7Kc+zxdZoZzzrnc1SDbATjnnMsuTwTOOZfjPBE451yO80TgnHM5zhOBc87l
OE8EzjmX4zwRuE1IMknbZPHzJ0rar4z39pNUkoHP7BF974ZpPOdSSVun63y1jaSDJb1YC+K4S9I5
2Y6jrvNEUAdJmi5pRXSx+VHS45JaxDhuhKQzkrZl5OJaxueXXnCXRo/pkq5I3MfM+pvZiAx8doGk
f0maK2mRpPGSTkn355QysxZm9nW6zyvpeklrJC2JHlMk3S+pcyXOsdnfQRXcAtwanW8LSf+Q9EP0
u/2fpN2TPvMXkr6VtEzSi5LaJbx3gaQxklZJeiJFvM0kPZjwb/dewtt3AH+Q1Lia3yeneSKouw43
sxbAzsCuwNVZjmcTFdxdt4liPwa4RtJBNRDS34Dvge5Ae+DXwI/p/pB0lirK8ZyZtQTaAUcDnYCx
lUkG1SFpV6C1mX0UbWoBfALsEsX0JPBa6c2JpP7AX4GTgC2B5cCDCaf8AbgZeKyMjxwanbdv9PN3
pW+Y2UxgMnBEOr5brvJEUMeZ2QzgDWCApGMljU18X9IlVSjCHyrp6+gO7A5JG/5OJJ0mqVjSAklv
Suqe8J5JOl/SVGBqjNjHABOBwoRzTJd0YPS8qaQnos+aREh4id+tS3SXP0fSN5J+U87H7Qo8YWbL
zGytmX1mZm8k7fNLSd9F3/sPCZ+zm6RRkhZKmhndgTdOeH+z751YxRZ9hwckvRbdxY+W1Cvh+IMl
fRnd7T4oaWScO3YzW2NmE4HjgTnAJdH52kp6Nfq9LIieF0Tv/RHYG7g/KpXdH23/s6TvJS2WNFbS
3uV89E+BkQlxfG1md5nZTDNbZ2ZDgcZAn9LfK/CKmb1nZkuBa4CfSWoZHf9vM3sRmJf8QZL6EC7y
Z5nZnOj8Y5N2GwEcVtHvy5XNE0EdJ6krcCjwGfAy0FNS34RdfkW4G66Mo4EiQmnjSOC06LOOAq4C
fgZ0BN4H/pF07FHA7kC/GLHvAQwAvipjl+uAXtHjEODkhGMbAK8AnwNbAQcAv5V0SBnn+gh4QNIJ
krqVsc9ehIvXAcC1Cb/HdYS70A7AwOj985KOreh7nwjcALQlfN8/Rt+jAzAMuJJQUvkS2LOMc6Rk
ZuuAlwgXeAj/rx8nlH66ASuA+6N9/0D4d7sgqr66IDrmE0JCbgf8HXheUn4ZH7l9FGdKkgoJiaD0
37U/4d+pNN5pwGpg2xhfb3fgW+CGKEGPl/TzpH2KgR1jnMuVwRNB3fWipIXAB4S7s1vMbBXwHOHi
X1ok7wG8Wslz32Zm883sO+AewkUM4Gzg/8ys2MzWEuqJCxNLBdH7881sRTnnnytpBTCKUEVQVonl
OOCP0fm+B+5NeG9XoKOZ3Whmq6P6+IeBE8o417GEC+A1wDeSxkVVHIluMLMVZvY54cK1I4CZjTWz
j6KSxHRCNce+ScdW9L3/bWYfR7+3Z9hYCjoUmBjdFa+NvuOsMs5Rnh8IF3HMbJ6Z/cvMlpvZEkLS
SY53E2b2dHTcWjP7E9CEjXf0ydoAS1K9IakV4cbjBjNbFG1uASxK2nUR0DLG9yog3CwsAroAFwBP
Jt3sLIliclXkiaDuOsrM2phZdzM7L+EC9CTwC0ki1Mn+M0oQAGuBRknnaQSsSdr2fcLzbwn/ASHc
Yf45qiJZCMwHRLgjT3VsWToQLg6XAvuliKlUlxSxlOoOdCmNJYrnKkId9GbMbIGZXWFm/aN9xhGS
qRJ2S7wAL49iRNK2UfXKLEmLCQmwQ9JHVPS9U547+TtamAWyKo33WxH+PUobV/+q0Di7GHgPaCMp
r6yDoyrE4qh6aiHQms2/Y6kFpLiIS2pKKKV9ZGb/l/DWUqBV0u6tKCOZJFlB+Pu8OUr4I4F3gYMT
9mkJLIxxLlcGTwT1TNSAt5pQTfALNq0W+o5QQkjUk00vsABdE553I9xtQrhgnR0loNJHUzP7MDGE
mHGui+48V7J5NUupmSliKfU98E1SLC3N7NAYnz0XuJNwEW5Xwe4ADxEaJHubWStCwlHSPlWdxncm
4a4XgCgxFZS9++aiarLDCSUeCG0FfYDdo3j3Kd01VaxRe8DlhBJYWzNrQ7gDT/6Opb4gqVpHUhNC
yW4GoeSYaCIJVTcK3WqbAFNifL0vYuzTl4SqJ1d5ngjqp6cIdcJrzeyDhO3PAadGjZ+StC2h7vvZ
pON/HzU4dgUuio4D+AtwZVTlhKTWko6tZqy3ApeVUR/9z+jz2kaNnRcmvPcxsFjS5VGjcp6kASmq
e4hivS16v2HUSHku8JWZbdZAmUJLYDGwVNJ20bHp8hqwvaSjFHocnU/oBVQhSY2iKpJ/RMfclRDv
CmChQjfN65IO/RFIHOPQklBanAM0lHQtm9/BJ3qdhKomSY0I7RwrgF+b2fqk/Z8BDpe0t6TmwI2E
qrIl0fENo3//PCBPUr429r56j3ADc2W03yBCKfLNhPPvS+gw4arIE0H99DdCveomjcRm9iZwBaEh
cRHhP/SThO55iV4CxhKqT14DHo2OfwG4DXg2qnKYQOhBUh2vEaoazkzx3g2E0so3wFuJ3ydqID2c
UNf+DTAXeIRQpZFKM+AFQhXC14SqpbhdDi8llK6WENohnit/9/ii0smxwO2EXjP9gDHAqnIOO17S
UsJ3eTk6bhczKy253QM0JfxOPgL+k3T8n4Fjoh5F9xIuqm8Q7tC/JZTSyqzqMrNPgUXaOFZgT2AI
obpmoTaOE9k72n8icA4hIcwmJJ7EUuDVhCRyBaF9a0W0DTNbQ+iwcCjhb/ZhQrKZDKDQZbYfZbcz
uRjkC9PUP1Fd7WxgZzOrsBunqz2iap4S4Jdm9m624ymLpIOB88zsqCzH8Sdgmpk9WOHOrkyeCOoh
SRcDQ8xs/2zH4ioWdXkdTbgT/j2hemjrCnpeOZc2NTEK0tUgSdMJjXxZvVNzlTKQ0He/MTCJ0CPM
k4CrMV4icM65HOeNxc45l+PqRNVQhw4drEePHrH2nToVevfObDyZ5PFnl8efXR5/eo0dO3aumXWs
aL86kQh69OjBmDFjYu1bVAQxd62VPP7s8vizy+NPL0nJg0VT8qoh55zLcZ4InHMux3kicM65HJfR
NoKoT/sSwnzua82sKJr75DnC5GfTgePMbEEm43DOOVe2migRDDazQjMril5fAQw3s97A8Oi1c865
LMlG1dCRhInOiH76CFjnnMuiTHcfNeAtSQb8NVrLdMtowWnMbKakLVIdKOks4CyA/PxuFBWl2mtz
xcXE3rc28vizy+PPLo8/OzKdCAaZ2Q/Rxf5tSZPjHhgljaEARUVFFrdv7qb9eGcA44H9CdO41H61
rR9yZXn82eXxZ1dti19lLS2UJKNVQ6Xzo5vZbMJc8LsBP0ZziJfOJT47cxGMBB4j3uqJzjmXmzKW
CCQ1j1aCIlqV6GDCQiYvAydHu51MWAQlQ4YQ1irvmbmPcM65Oi6TVUNbAi9Ea4M3BP5uZv+R9Anw
T0mnE5agq+5Sh+VoBWyfudM751w9kLFEYGZfk7BgdcL2ecABmfpc55xzleMji51zLsd5InDOuRzn
icA553KcJwLnnMtxngiccy7HeSJwzrkc54nAOedynCcC55zLcZ4InHMux3kicM65HOeJwDnncpwn
Auecy3GeCJxzLsd5InDOuRznicA553KcJwLnnMtxngiccy7HeSJwzrkc54nAOedynCcC55zLcZ4I
nHMux3kicM65HOeJwDnncpwnAuecy3EZTwSS8iR9JunV6PUTkr6RNC56FGY6Buecc2VrWAOfcRFQ
DLRK2PZ7MxtWA5/tnHOuAhktEUgqAA4DHsnk5zjnnKu6TJcI7gEuA1ombf+jpGuB4cAVZrYq+UBJ
ZwFnAeTnd6OoKN4HFhcTe9/ayOPPLo8/uzz+7MhYIpA0BJhtZmMl7Zfw1pXALKAxMBS4HLgx+Xgz
Gxq9T1FRkY0ZE+9zi4og7r61kcefXR5/dnn86SXF2y+TVUODgCMkTQeeBfaX9LSZzbRgFfA4sFsG
Y3DOOVeBjCUCM7vSzArMrAdwAvBfM/uVpM4AkgQcBUzIVAzOOecqVhO9hpI9I6kjIGAccE4WYnDO
ORepkURgZiOAEdHz/WviM51zzsXjI4udcy7HeSIo02JgTbaDcM65jPNEkNJ7wG+AG4CVWY7FOecy
yxNBSuMIv5rvgflZjsU55zIrG72G6oAjgSXAtkCnLMfinHOZ5Ykgpe7AH7IdhHPO1QivGnLOuRzn
icA553KcJwLnnMtxngiccy7HeSJwzrkc54nAOedynCcC55zLcZ4InHMux3kicM65HOeJwDnncpwn
Auecy3GeCJxzLsd5InDOuRznicA553KcJwLnnMtxngiccy7HeSJwzrkcV2EikNRA0k6SDpO0v6Qt
K/MBkvIkfSbp1eh1T0mjJU2V9JykxlUN3jnnXPWVmQgk9ZI0FPgKuBU4ETgPeFvSR5JOlRSnRHER
UJzw+jbgbjPrDSwATq9y9M4556qtvAv5zcDTQC8zO8TMfmVmx5jZDsARQGvgpPJOLqkAOAx4JHot
YH9gWLTLk8BR1fsKzjnnqqPMxevN7MRy3psN3BPj/PcAlwEto9ftgYVmtjZ6XQJsFS9U55xzmVBm
IkhF0iDCRf1NM7MK9h0CzDazsZL2K92cYteU55F0FnAWQH5+N4qK4sVYXEzsfWsjjz+7PP7s8viz
o9xEIOkp4DYzmyjpHOBs4AfgOOC0Cs49CDhC0qFAPtCKUEJoI6lhVCooiM63GTMbCgwFKCoqsjFj
4n2hoiKIu29t5PFnl8efXR5/einVrXcK5TUWdweKgCXR87OBC4HzgT0kdZPUqqzjzexKMyswsx7A
CcB/zeyXwLvAMdFuJwMvxQvVOedcJpTXWLwfoUH4J4TG4TbA1sC+QF70fo8qfOblwMWSviK0GTxa
hXPUQ0uAScDaCvYzYH3mw3HO5YzyGouflDQQOJaQBP5iZk9Jag6cbmZPxf0QMxsBjIiefw3sVp2g
65/5hE5aC4HrCBf7Hin2mwbcR0gahwI/I3Wzi3POxVdRY/F5wCHAajMbHm1rD/w+o1HlnEnAXEKB
y4AP2TwRGCEJAHQGXgYGAH1qJkTnXL1VbiIws/XAG0nbvgO+y2RQuadN9HMhodon1eBtI5QEOhP+
2QQsr5HonHP1W3mNxa9IOlxSoxTvbS3pRkkV9RxysfQntJtvAbQlNMMka0AYm/c9MB3oAmxbQ/E5
5+qz8koEZwIXA/dImg/MIXQD7UGorL7fzLzHT1oIOCB6lOdoQnXQMkISaJ7huJxzuaC8xuJZhFHB
l0nqQaiTWAFMMTOvk0i7BcC3hNLBZoWwiPBSgHMu3eJOQ21AczMbB5iklhUd4CpjDnAtcC8wg1Dg
cs65mhFnGuozCZPE/TXaVAC8mMmgcs9kYDHQLXr9URZjcc7lmjglgvMJ00UsBjCzqYRWTZc2HQiF
rnmEXkM+D59zrubEmXRulZmtVjRphaSGlDFRnKuq7Qjz631CGKbRPbvhOOdySpxEMFLSVUBTSQcR
Bpm9ktmwco2AvaKHc87VrDhVQ1cQWjPHEyaeex24OpNB5YShQ+Hrr7MdhXPOVTgNdR7wpJn9Cni4
ZkKq59asgYsvhm+/hVGj4Fe/ggMqGj/gnHOZU26JwMzWAR19gfk0atQIttsOli+HVatg++2jN+YD
nwGrsxiccy4XxWkjmA78T9LLhCGtAJjZXZkKqt7bcUdo2BBmzIA2bQg1bzcQ5g66ljAV9TbZjNA5
l0PiJIIfokcDNq497Kpjr73CY4PJwBJY0Cl6PRpPBM65mlJhIjCzG2oikJy2ri18uxju+BSWnwGr
twCvjHPO1ZAKE4GkjoQ5h/oTJp0DwMz2z2BcueW7ZnDzapi6HH5cD+Na+NI9zrkaE6f76DOEuoue
hIrs6YSRTy5dem4NzbeGDjtAgyaw28BsR+ScyyFx2gjam9mjki4ys5GEAWYjMx1Yzjn9dGjbFg5p
l+1InHM5Jk4iWBP9nCnpMELDcUHmQspRhYXhZ4vshuGcyz1xEsHNkloDlxAWzW0F/C6jUTnnnKsx
cXoNvRo9XQQMzmw4zjnnalp5axa/lfD8ypoJxznnXE0rr9dQx4Tnx2Y6EOecc9lRXiKo1poDkvIl
fSzpc0kTJd0QbX9C0jeSxkWPwup8jnPOueopr41g62h+ISU838DMjqjg3KuA/c1sqaRGwAeS3oje
+72ZDaty1Bm3CvgC6AR0LWe/pYRVxbYiXru7c87VPuVdvY5MeH5nZU9sZka4UgI0ih51ZGWzYYRl
F1oAtwFtUuyzkLAswyzCSp6/JeRM55yrWxSu1xk6eVjPYCxhBrUHzOxySU8AAwm33cOBK8xsVYpj
zyKs30h+frdd+vf/NtZnFhdD377VjXwuYYnmBoQhE6ny5VLCIGtF+/Uh3kDt8m0Wv60HVf+8NSU9
v//s8fizy+NPr7FjNdbMiiraL6OJYMOHSG2AF4ALCXUpswjTqg0FppnZjeUdX1RUZGPGjIn1WUVF
EHPXciwHPga6ANuWsc9o4MzoeUvgv0CT6n7wxvjNoKQEbr8d7rorrGNQB6Tn9589Hn92efzpJcVL
BDVyq2lmC4ERwE/MbKYFq4DHqZXTqzUD9qPsJAAwADgU6AecQdqnC33hBfj97+HDD+Hss2Hy5PSe
3znnIrETgaTmlTmxpI5RSQBJTYEDgcmSOkfbBBwFTKjMeWuP5sBNwIPAKaS9fWCffWDx4lAqyM+H
bt3Se/7aZMECmDUr21E4l7MqTASS9pQ0CSiOXu8o6cEY5+4MvCvpC8JspW9Ho5SfkTQeGA90AG6u
cvRZ1whoR9qTwMqVcO21MG0abLUVfPQR/OEP6f2M2uSll+CJJ7IdhXM5K06fx7uBQ4CXAczsc0n7
VHSQmX0B7JRiu69jUJH8fLjyynCXvGIFdO0Kf/xj5c5hBtKmr++/H046KVoesxYYMQL+8x/4+mtY
uxYuvxwGDoSjjsp2ZM7llFhVQ2b2fdKmdRmIxSVavBhat4LDfgLr10ODSjbnXH01fBItGzF+PLz9
NvzjH/Dyy2H72rXpj7myBgyAxo1DkmrcGFavhl12yXZUzuWcOCWC7yXtCZikxsBviKqJXAb1agt3
bQFtP4NZ20GTmIlg9uxQrVRSAt9+C9ttB02bwvPPw8yZoQfSoEGw/fbQMMuD4Dp0gD594OOPQywF
BaH045yrUXGuBOcAfyYMny0B3gLOz2RQDsh/HfLnAd2h00TCcIwYK5e1bw+9eoVSQMOGcNhh8P33
IUGsWAGrVoWqp/z8is9VExo1CtVezZvDqFHZjsa5nBRnGuq5wC9rIBa3ieWELqmKHpuNuUstLy9c
XIuKYM0aaNcuJIbmzcMd+LJl8ItflH38zJkwdiwMGbJx2+rVoXoqE8njuOM2Pt9uu/Sf3zlXoTiL
19+bYvMiYIyZvZT+kOqyecC90c/TSdFWXgmHE5aK/o4wunnn+If+9rebvjaD44+Hww8PbQTbbLP5
MWYwfHhIAp9/HpLIPvuEEsa998LChXBzHe7g5ZwrU5yqoXxgO+D56PXPgYnA6ZIGm9lvyzwy57xN
uHC3Ax4jLOhWVT0J8xwtALakWqOWpdB4DLDjjmXv8847YVikGbz4InTsCH/7G8ydG0oEZ50Vkky/
flWPxTlX68RpgdyGMIvofWZ2H2FgWF/gaODgTAZX97QlLPE8n02Xc6iqlkA30jF1RSznnht678yf
Hxpud9klJIOlS0P7QqtW0L17zcTinKsxcUoEWxGG0S6KXjcHupjZOkkxK65zxQHRz4XAQdkMpPLW
rAnTWRQUhK6qrVrBnDmw5ZbhuRTGHzSPBpiPHx8Gu7Vrl924nXPVFicR3A6MkzSC0Gq5D3BLNOXE
OxmMrQ5qSBh7VwetXw/vvQdTpkDLlqGtYL/94OCDQ9tCw4awaFFIGMuWwZ/+FBqkTzppY6JwztVJ
cXoNPSrpdcLkcAKuMrMford/n8ng6rXJk0Of+eYJUzitWwfkZSeeJk3gN78Jo3vXrAlVQLvvvuk+
BQXw9NPwyiuh8fi11+Czz+Caa6BHj6yE7ZyrvrjDVVcCMwmV39vEmWLClWHdujCz6G23hSmmp00L
21euhN/9DtauCY212bB+fSgF3HBDqPZJ5cQTYY89QpfStWvhlFM8CThXx8XpPnoGcBGhD+M4YA9g
FOBzBlWFFLppTpkSZt2cPz9sv+WWMBL4+xL4aFaYc6em9e8fHgC7lTE7eF4eTJ0KO+wQqopKSmou
PudySfJ8YRkUp43gImBX4CMzGyxpO+CGzIZVG60GfiCsY5xPWHXzTWASYV2CmIOhGjSAQS1g9Txo
sBJ26ASNC0K9fIMG0EBlX4Qr4+23w1w+nTtX/1zJrr0Wttgi9CQqnbOodFK7tecQZmV1zlXZJ5/A
hAlw6qk18nFxqoZWmtlKAElNzGwyYV3GHGKESVivA/4PWAt8BfwdmAbcE22LYy4cMxMeOgru2R6a
vB6y/uDBYarp5s3DXXdVLVwIr74KTz4ZHu++m/6qpk6dQtJq3jw0FBcXw/vvh3EIixfDuHGh6sg5
VznLl4eS9ltvhZqD+fNhyZKMf2ycEkFJtMDMi8DbkhYQbo1zyBrCPHudCOsULyU06opQUsgn/poE
gkbRhT6vIRty8ZFHhp8dqhnq8uUwbBj88EOYxnrWrFDvn0kvvRQSTrt2MHcePPIIXHddGIPgnIvH
DP7v/0JJoEGDMFXM6aeH0vfNN2f0/1OFJQIzO9rMFprZ9cA1wKOElcVySGPgBGAZMARoTRj5ew6w
F3Ap8Xv7tCdM3bSYMFjs6OqHN2dOeAB06RKmkGjdGtq2hQsvrH49o9nmpYq1azfWYV56KfTsGZJQ
gwbhtScB5ypHgosvhsLCMLCz9P/wZZdl/P9TuSUCSQ2AL8xsAICZjcxoNLXaT6JHooHEmhF0Mwew
cfBZNZiFmUVvvz28vuyy0CX1gAPCZG7Tp4e2h4rOUVGi+O9/w9iBI47YuO3ii8PEdAcfHKqD1q2D
X/0KRjWCmT94TyLnqqJtW2jWDObNC21wrVvXyGj+cksEZrYe+FxSPV4wtw4qvTtfsQJuvTU0LH3y
SXi+cmXocbTttuEivcUWZZ9n/vzQZXVdGesMrVgRppd44w14883w/PPPw5xD33wDTz0VShzNmoVk
dOyxYaxBYWH6v7NzucAs3Fhde20YtFlQsLG0n0Fx2gg6AxMlfUyoGwHAzI4o+xCXMWPGwOuvhz+U
Ro3C3cI//xnu6o85JmyL49FHQzfQqVPhiivgwAPhkIRR0WvWwFVXhVJFXl6o8jnppNBQ3KxZaMBa
vTqUEpo02ThFdYO8sBCOc67yJLjppo2vK7tEbRXFSQQ52FW0lrrlljAiecGCMEHcJZeEC3ppD51H
HoGzzw49eSrSti1MnBimjvjuu/A6UaNGoarpzjvD7KN5eSEBXH55mJa6V6+QLLp29eklnKvj4kwx
MVJSd6C3mb0jqRlZmwchxx14IIweHap0Bg0K9fCDB8O//x3e33//itsESh1wAPzrX+Ei3rhxmDco
WefOISHMnh1KBNtsE4qql14aEsfSpaE04Jyr0+KMLD4TOIswyX4vwmykfyEtrZ05bM2a+NU4pTp2
DL2CunYN1S8NG4b5gGbPDu8PHBj/7rxx41DXv9tuYdbRVMetWRMeN90U9n/qqdBovOWW4X2fedS5
eiFO1dD5hAnnRgOY2VRJ5bRAugotXQpXXgk/+xnstVf8hNCjBzzwQLholzYYH388nHBCeF6ZgWNN
m8K++4bnB5SR0xs1Cg1Wpe68M/75q2vBgjBgrXHjmvtM53JUnESwysxWK7pjlNSQMNTWVcWaNaFx
trg43MkvWBASQhzSxjv30p+Js5fWF2ahoXr33eHkk70NwrkMizPFxEhJVwFNJR1EWLLylYoOkpQv
6WNJn0uaKOmGaHtPSaMlTZX0nKQcuOVby4YpKBo1gr33Dv2D8/PhsMOyGlmtU1wcRlNOmxZmaT3/
/NCN1TmXMXESwRXAHGA8cDbwOnB1jONWEZa43BEoBH4iaQ/CQrx3m1lvwoK8p1cl8LrjU+A84ELC
NBWEaZxvvhlOO63y7QTptmzZ5tuyNQ02wHbbhSkxli0LvaFOPdW7ozqXYXESwZHAU2Z2rJkdY2YP
m1V8pbBgafSyUfQwwvTVw6LtT1Lvp6t4GmhFmKbi2bCpe/ewAPy++4beONlSUhLuuFclrDg6ZkwY
ZJYtEnz9Ney8M3TrljpROefSShVd0yU9Trh4v0e4kr1pZrGm2pSUB4wFtgEeAO4gTGe9TfR+V+CN
0iksko49i9Bbifz8brv07/9trC9UXAx9+8batYbMJBSODGgGbFnu3jUSv62HkhlhEZwlS8K4gybR
1Npr14XE0DQf2rYLYwdSmTcXmjXf7G49LfHb+qR2gZprI6h9fz+V4/FnV22Lf+xYjTWzFH3DNxVn
HMGpkhoBPwV+ATwo6W0zOyPGseuAwmj20heAVL+ilJnIzIYCQwGKiopszJiKPi0oKgo3tbVHY+AN
wtCLigs/NRK/CX59VZg2uu360DPnggtCb6YPPwwN0O3awdVXh7EDiWbMCAE++yz06QO77AIHHbRh
ZHFi/JOGTQKg3zH9Khlg9kpJte/vp3I8/uyqbfHH7WcRp9cQZrZG0huEi3ZTQnVRhYkg4fiFkkYQ
VjdrI6lhVKoooN5Pad0eOC3bQWxKCm0U770X5iZq2jRUB02YEEYb50XTRCQnAQi9nJ59NsyZ/t//
hmmu9998sbpJwyaxuGTxhuc5FzBqAAAfVElEQVRQlYTgnKsJFd56SfqJpCcIK7EcAzxCmH+oouM6
RiUBJDUFDiS0lr4bnQfgZOClKkXuqicvL6xg9vDDoSy7fj106BDaDO67b+P6CMkGDAjLWa5fH6qU
zjyzfnZhdS6HxCkRnEJoGzjbzFZVsG+izsCTUTtBA+CfZvaqpEnAs5JuBj4jrG/galpBAbz2Wnhe
Or10t27hAfCT5Cm3E3ToEFZT++KLMsue/Y7p5yUB5+qIOG0EJyS+ljQI+IWZnV/BcV8AO6XY/jVh
pLKrK1asCCWA0jv/c84JP/feO3sxOefSJlYbgaRCQkPxccA3wL8zGZSrpNKeX5kagXv33aFN4Lbb
KnWYlwScqxvKbCOQtK2kayUVA/cD3xO6mw42s/tqLMJa4w3gAsLA6lo2w8Zrr4U1CtJtypTQBvDJ
J2H66zPOgPHj0/85zrmsKq9EMBl4HzjczL4CkJTFkUbZtBp4jjAG4DXgIKBNViMCwjoCc+eGO/YG
DcK00R07htlJ06FHj7DuwHffhdcFBal7EkUmDZvEygU9CR3Lag9vq3CufOX1Gvo5MAt4V9LDkg6g
Jkf21CqNCEMgZgHdgRbZDafU6NFhVbIvv4RJk8Lzjz9Ova8ZPP545UbqNm4cupG2bRvGFUgpp3uY
NGzShu6i61av23DhrY7Sc6bjHItLFrO4ZHFazulcfVRmicDMXgBekNScMBLqd8CWkh4CXjCzt2oo
xlpAhK//A9CJmE0rmXfMMWEt4dKFaQ49NPVMpt98A59+GtYebtQIevcOM3vGcfjhcNxxobvpokXp
i70MpRfqxDEIfifvXGbF6TW0DHgGeEZSO+BYwkR0OZQIIIwQ7pHtIDYlhTv8nj3D62XLUjcYT58O
//hHGDz297+Hlc7iJoKtt974fIvUy1CUXqgnDZtEXuO8WnPhTowr8bVzblOVurU1s/nAX6OHy4bi
Yvjf/0LDLYTVwwoKwvMZM1IfM3gwPPMMzJsXqnbOPTcjofU7ph/5t1b/HOAXb+dqUi2p43CxPPxw
6MEzb15oE7jmmk0bb3v1Sn2cGeyzT0gI774L69bVTLy1hCcT58rniaAuKSiAF18M8/106xZ/agcJ
fv3r8Lz0Zy1X1y/eXqJxdYkngrqkb9/QRXSrrcKaBjm2nq9fXJ3LDE8EdUnXrnDPPWHK51WVmfap
ZlR1HEFdusBXFGuqXk/l7e9cbZDF5bFcpeXlhfaB116rVTN+VmccQXI//4rOX95+iftWtK0y8fnY
A1ffeYmgNpk9G+hIynF7a9fCBx+EAWPjxoVEsOOOYSRxHZLJO+RJwyYx5bUpG16XjCqhYGBBWu7O
497pe68nVxd5iaA2WLs2dAu99towFmDFis33Wb8e/vnPMChs/nx47DGYM6fmY02h3zH96HdMP1oV
tNpkHEGqu+nGM76h47P3bnJsq4JWtCpotclFM/HYxPMn75cpyaWQklElGf9M57LFSwS1wYwZcMcd
YZK32bNh0oKwBGSixo3DojFXXRXaB/r2hX6VvCB+8UU4pmHm/9mTVyjT6lW0/OgtVo4qptnsycw4
/xZWbt2XXpccvdlxkHpkcawEkDAfYMHAgrSti1DZc3lJwNUlnghqg+7dQ1VPp07wZYPNk0CpBg3C
qOCddgpJI64VK0Lp4Y47QjLp3x9atkxP7AnKHVAmYSPfp+OMaaxu3JLGb73O/MKG9KJ2XjS9isfl
Ek8EtcU550D79rB/ORfovn3DA2CvveKf+/HHw/rCo0eHEkffvqH3UQalunv+6sezsZuuRatW0ah/
T5ofPyTlcVC1C3DivmU9ry5PCK4+8kRQW/TvH342y8C5u3cP6wgsXQpTp8Iee2TgQzaXfNHU+vX8
2GY7fmg3gIHtf6zUsVX9zOryC7/LBd5YnAsKC0O1UteuYZRxZUoTaTRtRlNGaSDfLmjJuK2GVLsB
tjZ37azNsTmXzEsEuaBLF9h3X2jSBJYsKbsNogY0bVe7Fq1xznkiyA0SXH11mJpi1ixo3TorYRQM
LGD5/OUbnldHcq8kqB3VOD6yOD3WrFlDSUkJK1euzHYolXL77aEneE3Lz8+noKCARo0aVel4TwS5
oqAg4aLUOSsh9Dum34bqIL8wuvKUlJTQsmVLevTogVKtsVFLmW3sz1Fzn2nMmzePkpISepauTVJJ
nghyRPIddHUvxFW90z34TwdX+fzJA8zSMVI4U43LXhKonpUrV9a5JJAtkmjfvj1zqjHA1BOBq7R0
J5Xkc0PmlqqsbNWNX9Czx5NAfNX9XWUsEUjqCjxFWOR3PTDUzP4s6XrgTKA0fV1lZq9nKo46zyz1
8pOVlK4RttlQVnKI+z2y8b3r2u/Y5bZMlgjWApeY2aeSWgJjJb0dvXe3md2Zwc+uH378EW65Be6+
O3T/rKZ0XZwymVRSVa2ksxtm3Kqb0venvLpxBLdf3HPL9OnTGTJkCBMmTNiw7frrr6dFixZceuml
m+x7yimnMGTIEPr1O6amw0yLjCUCM5sJzIyeL5FUDGyVqc+rd15/HZ57LvTyOessuPxy6N0721Ft
kI2768omn3T04Fk4fWHsfV1uWrt2bbZDqDaZWcV7VfdDpB7Ae8AA4GLgFGAxMIZQaliQ4pizgLMA
8vO77dK//7exPqu4uOZb7dNpQ/zr1sH338HKVWEeoq4FpJyeupZJ/P0vLlkEQKuC7HRXXbkgzOK6
bnVYozmvcR4A+W3LHstQGn9p7KuXrAagccvGWfselVFf/v5vv72YTp0q90VK3gyJvuCQ9NykzJgx
nfPOG8JLL20sETzwwPU0a9aCkSNfpbBwTz777H8MHnwEU6aMp0mTfKZMmciCBT9y2WV3sd9+Q5gx
YzpXXHESK1YsA+APf7ifnXbak48/HsGDD15PmzYd+OqrCfTrtwu33fZ0ter6Z80q5rLLNv2djR2r
sWZWVNGxGW8sltQC+BfwWzNbLOkh4CbCPJE3AX8CTks+zsyGAkMBioqKbMyYeJ9XVARx962NNsS/
XvC7e8Ko4B9/hCuuyHZosZTGP2nYpA3VKtsO2RbIRtVKuOC/dclbQLweS6Xxv3XJaAC+fT/cgHTf
u3vsHk/ZVF/+/iub0CYNm0QrLY5epKeDQbNmYQxm4iS/HTtCixbhvYYNF/LJJyOBUDU0a9Z0/va3
kTRpMo3Bgwdz2mlf0aPHFvzvf2+Tn5/P1KlTOfHEExkzZgyzZ8OXX37GxIkT6dKlC4MGDWLBgv+x
VzVG/Uub/9vHzSsZTQSSGhGSwDNm9m8AM/sx4f2HgVczGUOd1aAB/PnP2Y6iykpGlbBy0coNz6Hm
E0FpVdDyecs3eR2njaP0ol+ZJOLql7Luzku3H3/88ZtsP+6442jQoAG9e/dm6623ZvLkyfTs2ZML
LriAcePGkZeXx5SEWYN32203CgrCwMrCwkKmT59erURQHZnsNSTgUaDYzO5K2N45aj8AOBqYkOp4
V7tVdCEtaxRxOvv+xz1Xp8JOsc9flTWXXfZlogND+/btWbBg01rr+fPnbxi01TxpudjkxCGJu+++
my233JLPP/+c9evXk5+fv+H9Jk2abHiel5eX1baGTJYIBgEnAeMljYu2XQWcKKmQUDU0HTg7gzG4
DIgzjiDVNNDpnBYizrnK6oGUfGzikpalay6XHlvdqTBczUl3ibNFixZ07tyZ4cOHc8ABBzB//nz+
85//cNFFF/H4449vtv/zzz/PrruezLRp3/D111/Tp08fFi1aREFBAQ0aNODJJ59k3bp1aY0xXTLZ
a+gDUrdu+piBHJGu/5hl9f5xLtOeeuopzj//fC655BIArrvuOnr16pVy3z59+nDyyfuyZMmP/OUv
fyE/P5/zzjuPn//85zz//PMMHjx4s1JEbVEjvYaqKzQWx2sBqy+NZbVdWXfhFcVflZJAciIoXbe4
OvX3ZU1hcdzlPZkwrWmZn1nb1ZW/n7JsbCwupm8d7P40aVLlV5BNl1S/M6mW9BpyLlFVGo4r0ybg
awo7V3meCFyVVLWxt1XXVhuel3eeVO8n373HPVdciWsu++RxLpd4InBpk+1eN7V1jQLnajtPBK7a
EuvTk3vdJIrTxW/DHD+vlT/HT6pzTRo2iVmfzwJCnX46eCJxucATgcuYiqp3qivVuXxuIOcqzxOB
q7bEO/K8xnkb7tarVU1Thc5sJaNKWLNszYbnlf5M53JU9ec2djmpdGBWon7H9Ct3QrfK6FTYKfaI
YOcyIS8vj8LCQgYMGMDhhx/OwoXpK21ef/313Hln7ZmJ3xOBq7TSu/3FJYvLHNzV75h+tCpotaH/
fUVdPpOXoUw8Nq6CgQU0bt6Yxs0bUzCwwEcFu2pp2rQp48aNY8KECbRr144HHnigUsfX1lHEqXgi
cBVKdfefznOnSiqVWYEs8ZjOO3em886dK5V8XH2xkjBrzcq0n3ngwIHMmDEDgBEjRjBkyJAN711w
wQU88cQTABx0UA9uvPFG9tprL55//nkefvhhdt11V3bccUd+/vOfs3z58rTHlg7eRuDKlWpeobi9
f+K2EaSzp09FpYB0LFbjaqOVwM1ACVAAXA3kl3tEXOvWrWP48OGcfvrpsfbPz8/ngw8+AGDevHmc
eeaZAFx99dU8+uijXHjhhWmJK508EbgqSeuFM42znPgFPVfNIiSBHoRSwazoedWtWLFiw/TQu+yy
CwcddFCs4xKnp54wYQJXX301CxcuZOnSpRxyyCHViilTvGrIlaus+vqKqlYq00aQaRW1QXjyqA86
EUoC06Of1e9oUNpG8O2337J69eoNbQQNGzZk/fr1G/ZbuXLTqqjEieVOOeUU7r//fsaPH8911123
2b61hZcIXIWSL5RxpqGuyrmzfUHO9shoVx35hOqgWYQkkJ5qIYDWrVtz7733cuSRR3LuuefSvXt3
Jk2axKpVq1i5ciXDhw8vc0GZJUuW0LlzZ9asWcMzzzzDVlvVzmXbPRGk3WpgLdAs24FkXbov7Olc
vD7bScdlQj7VrQ4qy0477cSOO+7Is88+y0knncRxxx3HDjvsQO/evdlpp53KPO6mm25i9913p3v3
7my//fYsWbIkI/FVlyeClFYAnwKdga0rcdz3wB3AUuCXwAHpD60a0jk5WzobWbN9UY47RYbLLUuX
Lt3k9SuvvLLh+e23387tt9++2TFvvz2dDh02vj733HM599xzN9vv+uuvT1uc6eCJIKXngTeAFsBt
QLuYx40ElgNbEJZqrj2JIJ3VOZDei3fc+YcqG7/PIOpcPN5YnJKSHnF1I3RjKwG2yUBcdUucvvpx
BqdlWmIDcukUGc7lEi8RpHQs4ULeCWhbieP2BloTqoZ2zkBcVZeJxb1rSnXv7Ova93WupnkiSCkf
GFiF4wTsmOZY0qcmL4hxB5RVJkFlOv7EhWmcyyWeCFzWVfUCX1dLOM7VNp4IXEbU5aoo53KNNxa7
jMlkf/3kRmafQM6l2x//+Ef69+/PDjvsQGFhIaNHjy5z33RMK73ffvsxZsyYap2jqrxE4JyrPxYv
hlbVn7xw1KhRvPrqq3z66ac0adKEuXPnsnr16jQEmFq2p6zOWIlAUldJ70oqljRR0kXR9naS3pY0
NfpZmW45zgG1ay4jV0ssWABXXglpWEBm5syZdOjQgSZNmgDQoUMHunTpQo8ePZg7dy4AY8aMYb/9
9ttwzOeff86pp+5P7969efjhh4Hyp6zu0WPTKasBnn76afbcc08GDBjAxx9/DMDIkSMpLCyksLCQ
nXbaKSOjkzNZNbQWuMTM+gJ7AOdL6gdcAQw3s97A8Oi1c5XmCcABsGYNPPII3HcfTJ4M994bXq9d
W+VTHnzwwXz//fdsu+22nHfeeYwcObLCY7744gseeug1Ro0axY033sgPP/xQ4TGlU1afcMIJACxb
towPP/yQBx98kNNOOw2AO++8kwceeIBx48bx/vvv07Rp+ufCylgiMLOZZvZp9HwJUAxsBRwJPBnt
9iRwVKZicM7lgIYNYYstYPRo6NUr/NxiC8jLq/IpW7RowdixYxk6dCgdO3bk+OOP33AnX5YjjzyS
/PymdOjQgcGDB2+4oy9P4pTVACeeeCIA++yzD4sXL2bhwoUMGjSIiy++mHvvvZeFCxfSsGH6a/Rr
pI1AUg9gJ2A0sKWZzYSQLCRtUcYxZwFnAeTnd6OoKN5nFRcTe9/ayOPPLo8/u0rjv/12sNjrVIgG
nfaj89qn0TfzsLzmzOw8mPXFlZkVIJU8tthiP44/fj/atNmeJ554kvXrG1JcvJ727aG4eCXLl8Ok
STBnDpiJlSvD60WLoKRELFnSkMWL1zMp6sswa9ZKZswI+6xZAyUlzVm2LLy3fDl8+6027LtmDXz5
pTjiiCvYbrvDeO+91ykq2oNHHnmHrbfebrNoZ82Ck06q2jfNeCKQ1IIw8c5vzWyxFO8fx8yGAkMB
ioqKLG5jelERZKnhPS3qcvyThk3iuMt7MmZM3Z3GuS7//qH+xF9cDH37VuLAWcvhl0PgkEPgzTdp
3XUZdGpZ5Ti+/PJLGjRoQO/evQH4+9/HMWBAdxo2XMHSpWPZe++f8vDD/6JZM+jXDzp2hBdffIkz
z7ySLbdcxmefjeChh25l3bp1XHPNJHr1ClNWjx07nCFD9qJfP2jUCPr0YcMkdc2awejRz3HqqYP5
4IMP6NChNbvv3ppp06Zx1FHbc9RR2/P116NYu3Yy/fptngikzf/tY15uM5sIJDUiJIFnzOzf0eYf
JXWOSgOdgdmZjMFlns/e6bKuUyf49a/D89Kf1bB06VIuvPDCDVUx22yzDUOHDqW4uJjTTz+dW265
hd13332TY3bbbTfOPfcw5s37jmuuuYYuXboAxJ6yGqBt27bsueeeLF68mMceewyAe+65h3fffZe8
vDz69evHT3/602p/v2QZSwQKt/6PAsVmdlfCWy8DJwO3Rj9fylQMzjlXFbvssgsffvjhZtv33ntv
pkyZstn20mmlJ00KJYREZU1ZPX369E1ejxgxImUs9913X6yYqyOTJYJBwEnAeEnjom1XERLAPyWd
DnxHmOHN1WGJk8L57J3O1T0ZSwRm9gFlz+Fceybqd2njk7Y5Vzf5FBPOuVrJ4ncbynnV/V15InDO
1Tr5+fnMmzfPk0EMZsa8efPIz8+v8jl8riHnXK1TUFBASUkJc+bMyXYolTJrVvwum+mUn59PQUFB
lY/3ROCcq3UaNWpEz549sx1GpZ10Ut0cx+FVQ845l+M8ETjnXI7zROCcczlOdaFVXtIc4NuYu3cA
5mYwnEzz+LPL488ujz+9uptZx4p2qhOJoDIkjTGzOjv/osefXR5/dnn82eFVQ845l+M8ETjnXI6r
j4lgaLYDqCaPP7s8/uzy+LOg3rUROOecq5z6WCJwzjlXCZ4InHMux9WbRCDpJ5K+lPSVpCuyHU9F
JD0mabakCQnb2kl6W9LU6GfbbMZYHkldJb0rqVjSREkXRdvrxHeQlC/pY0mfR/HfEG3vKWl0FP9z
khpnO9bySMqT9JmkV6PXdSZ+SdMljZc0TtKYaFud+PsBkNRG0jBJk6P/BwPrUvyJ6kUikJQHPAD8
FOgHnCipti+T9QTwk6RtVwDDzaw3MDx6XVutBS4xs77AHsD50e+8rnyHVcD+ZrYjUAj8RNIewG3A
3VH8C4DTsxhjHBcBxQmv61r8g82sMKHvfV35+wH4M/AfM9sO2JHw71CX4t/IzOr8AxgIvJnw+krg
ymzHFSPuHsCEhNdfAp2j552BL7MdYyW+y0vAQXXxOwDNgE+B3QmjQhtG2zf5u6ptD6CAcLHZH3iV
sCJgXYp/OtAhaVud+PsBWgHfEHW4qWvxJz/qRYkA2Ar4PuF1SbStrtnSzGYCRD+3yHI8sUjqAewE
jKYOfYeoWmUcMBt4G5gGLDSztdEutf3v6B7gMmB99Lo9dSt+A96SNFbSWdG2uvL3szUwB3g8qpp7
RFJz6k78m6gviSDVUhDeL7YGSGoB/Av4rZktznY8lWFm68yskHBnvRvQN9VuNRtVPJKGALPNbGzi
5hS71sr4I4PMbGdCle75kvbJdkCV0BDYGXjIzHYCllFXqoFSqC+JoATomvC6APghS7FUx4+SOgNE
P2dnOZ5ySWpESALPmNm/o8116jsAmNlCYAShraONpNIFm2rz39Eg4AhJ04FnCdVD91B34sfMfoh+
zgZeICTjuvL3UwKUmNno6PUwQmKoK/Fvor4kgk+A3lGPicbACcDLWY6pKl4GTo6en0yod6+VJAl4
FCg2s7sS3qoT30FSR0ltoudNgQMJjX3vAsdEu9Xa+M3sSjMrMLMehL/3/5rZL6kj8UtqLqll6XPg
YGACdeTvx8xmAd9L6hNtOgCYRB2JfzPZbqRIY+PNocAUQj3vH7IdT4x4/wHMBNYQ7i5OJ9TxDgem
Rj/bZTvOcuLfi1Dt8AUwLnocWle+A7AD8FkU/wTg2mj71sDHwFfA80CTbMca47vsB7xal+KP4vw8
ekws/T9bV/5+olgLgTHR39CLQNu6FH/iw6eYcM65HFdfqoacc85VkScC55zLcZ4InHMux3kicM65
HOeJwDnncpwnghwnqX00++M4SbMkzUh4vdnMldHsiufEOG9DSQvL2G6SbkvYdoWkq6v/bUDS05KO
Sse5KvicE6IZJ99J2r6NpBXR769Y0hOlA7wk7S7p7jLOV1I6rqGacV0q6RfR86clfRPFMlbS7tU8
9x6SPlCY5XeypKGSmko6WtLvo31+Jmm7GOd6XtLW1YnHpY8nghxnZvMszP5YCPyFMHNlYfRYneKQ
dkCFiaACK4DjJLWr5nnSKmFEbhxnAGeZ2YEp3vsy+n1uD/QEfg5gZqPN7HfVjzS1aKT3ScBzCZt/
F8VyDfBQJc7VMOl15+i8F5tZH8Isv8OBFmb2gpndEe36M6DCRED4W/t93HhcZnkicGWSdJmkCdHj
wmjzrUCf6C7zVkmtJP1X0qeSvojmwKnIauAxwhTKyZ+5yR29pKXRzwMV1j8YFs31frOkX0v6JPrc
HgmnOUTS+5KmSPppdHxDSXcprEHwhaQzEs77jqRnCQPMkuP5lcKc+RMk3RJtu5EwHcUjkm4t60ta
mPztE6KJ36LPejF63lFhvvpPJT1EwjxBkk6O4hwn6UFJDaL4/5YQy29SfORBwCdmti7Fe+8B20Tn
7y3pzaiU8J6kbRN+93+S9C5wS9LxFwKPmtnH0Xdbb2bPmdkcSWdIukfS3oRBhXdHsfeR9HHC9+qb
8HoEYervvLJ+f67mVOYOyOUQSbsBvyTM/5IHfCxpJGFirW2iu8zSu9AjzWyJpC2A/xGmRK7IfcA4
SX+qRFg7EiaGW0SYwvhBM9tV0iXABcCl0X5dgX2B3sA7krYhjNyebWa7SWoCfCTprWj/PYB+ZvZd
0u+gALgZKIo+8x1JQ8zsWkn7AxeY2biyglWYumJX4LwUb98AvGtmt0g6kqiUJWkAcDSwp5mtlTSU
MIXENMKUzdtH+6WqRhoEjE2xHeBwYHz0fChwhplNkzQIuJ8wxQNAL+AAM1ufdPwA4K9lfVcAM3tf
0uvAMDMrTXgrJQ0wswnAqcDj0b7rFOZJGkAYXeyyyEsErix7A/8ys+VmtoQwhH6vFPsJuE3SF8Bb
QFdJHSo6uYWJ3v4OnF+JmEab2Y9mthL4Gngz2j6esLZDqX9Gd6xfEqYn70240J2qMO30aKBNtB1g
VHISiOxOmMNnrpmtieKNM0Nmn+hz5gFfmdnEFPvsAzwNYGYvAUui7QcSkseY6Bz7Ei7OX0Xn/bOk
QwiJKVlnwtTIie6OznMqcGaUQPYA/hVtfwDokrD/8ymSQHU8Svi9NwSOJUytUmp20me7LPESgStL
qimNU/k10BrYObqDLQHyYx57F6Hq5G+E6iIIK581gA0rzyX+ja5KeL4+4fX6pP2S500xwvc5z8yG
J74h6UDCFMKpxP0dJPvSzAoldQHek3Somb2eYr9U87sIeMzMrtnsDWkHwpTNvyG0O5yVtMsKNv/d
/6707jw6R1tgbmmJLoWyfhcTgV2A18p4vyzPA1cRSoqjohuAUvlRzC7LvETgyvIecHTUK6QFcCTw
PuHOtWXCfq0JVS5rJR1EJRZCMbO5hOmHT0nYPJ1wwYFQRVKVOuRjFWxLqCaaSig9nKeNPXj6RFU3
5fkIGKzQs6ohoYpmZNwgLEyzfGX0SPYeoeoNSYez8Xf6DqEhvUP0XntJ3SR1JKyG9TxwHWHK42TF
RO0A5cS0AJgp6ejo/A0k7Rjj69wHnC6pKDpOUVtGx6T9Nvn7MLPlwH8J1U+PJ+3bm5BgXJZ5InAp
RY2C/yDcsX9EWIBjvJn9SKi2GB81lP4N2FNh8fFjCRfdyriDTVdx+itwUNSoWMimpYC4viJcaF8h
9OxZHZ13KqFdYgKhB025JWIzKwGuJTRsjgM+MrPK3hEPA9pJGpi0/TrgQEmfEmYPnRF95nhC+8E7
CdVtWxIS2ntRdc7DhLvsZK8TqpIqcgJwjqTSmT8rbOCPktovgD9LmkyYcnkPYGnSrv8Arooai3tE
254hzLK7oTQWlZYWmVlyVZbLAp991Ll6RNLLhNXivs52LKUkXUGYDvuGhG2/J5Qkn8xeZK6UtxE4
V79cTmiArRWJQNIrhNLM/klvzSNqLHfZ5yUC55zLcd5G4JxzOc4TgXPO5ThPBM45l+M8ETjnXI7z
ROCccznu/wEGI2OMZQ1TzgAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[99]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Total Fares by Area Type</span>
<span class="n">Total_Fare</span> <span class="o">=</span> <span class="n">ridesharedf</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;type&#39;</span><span class="p">])[</span><span class="s1">&#39;fare&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
<span class="n">labels</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;Urban&quot;</span><span class="p">,</span> <span class="s2">&quot;Rural&quot;</span><span class="p">,</span> <span class="s2">&quot;Suburbs&quot;</span><span class="p">]</span>
<span class="n">colors</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;purple&quot;</span><span class="p">,</span> <span class="s2">&quot;yellow&quot;</span><span class="p">,</span> <span class="s2">&quot;red&quot;</span><span class="p">]</span>
<span class="n">explode</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="o">.</span><span class="mi">1</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;</span><span class="si">% o</span><span class="s2">f Total Fares by City&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">Total_Fare</span><span class="p">,</span> <span class="n">explode</span><span class="o">=</span><span class="n">explode</span><span class="p">,</span> <span class="n">labels</span><span class="o">=</span><span class="n">labels</span><span class="p">,</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">autopct</span> <span class="o">=</span><span class="s2">&quot;</span><span class="si">%1.1f%%</span><span class="s2">&quot;</span><span class="p">,</span> <span class="n">shadow</span> <span class="o">=</span> <span class="kc">True</span><span class="p">,</span> <span class="n">startangle</span><span class="o">=</span><span class="mi">80</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axis</span><span class="p">(</span><span class="s2">&quot;equal&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
SZLyYQwAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[100]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Total Rides Per City</span>
<span class="n">Total_Rides</span> <span class="o">=</span> <span class="n">ridesharedf</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;type&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">count</span><span class="p">()[</span><span class="s1">&#39;ride_id&#39;</span><span class="p">]</span>
<span class="n">labels</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;Urban&quot;</span><span class="p">,</span> <span class="s2">&quot;Rural&quot;</span><span class="p">,</span> <span class="s2">&quot;Suburbs&quot;</span><span class="p">]</span>
<span class="n">colors</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;purple&quot;</span><span class="p">,</span> <span class="s2">&quot;yellow&quot;</span><span class="p">,</span> <span class="s2">&quot;red&quot;</span><span class="p">]</span>
<span class="n">explode</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="o">.</span><span class="mi">1</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;</span><span class="si">% o</span><span class="s2">f Total Rides by City&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">Total_Rides</span><span class="p">,</span> <span class="n">explode</span><span class="o">=</span><span class="n">explode</span><span class="p">,</span> <span class="n">labels</span><span class="o">=</span><span class="n">labels</span><span class="p">,</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">autopct</span> <span class="o">=</span><span class="s2">&quot;</span><span class="si">%1.1f%%</span><span class="s2">&quot;</span><span class="p">,</span> <span class="n">shadow</span> <span class="o">=</span> <span class="kc">True</span><span class="p">,</span> <span class="n">startangle</span><span class="o">=</span><span class="mi">80</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axis</span><span class="p">(</span><span class="s2">&quot;equal&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
gg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[101]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Total Drivers by Area</span>
<span class="c1">#Total Rides Per City</span>
<span class="n">Total_Drivers</span> <span class="o">=</span> <span class="n">ridesharedf</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s1">&#39;type&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">agg</span><span class="p">({</span><span class="s1">&#39;driver_count&#39;</span><span class="p">:[</span><span class="s1">&#39;sum&#39;</span><span class="p">]})</span>
<span class="n">labels</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;Urban&quot;</span><span class="p">,</span> <span class="s2">&quot;Rural&quot;</span><span class="p">,</span> <span class="s2">&quot;Suburbs&quot;</span><span class="p">]</span>
<span class="n">colors</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;purple&quot;</span><span class="p">,</span> <span class="s2">&quot;yellow&quot;</span><span class="p">,</span> <span class="s2">&quot;red&quot;</span><span class="p">]</span>
<span class="n">explode</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">,</span><span class="o">.</span><span class="mi">1</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;</span><span class="si">% o</span><span class="s2">f Total Rides by City&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">Total_Drivers</span><span class="p">,</span> <span class="n">explode</span><span class="o">=</span><span class="n">explode</span><span class="p">,</span> <span class="n">labels</span><span class="o">=</span><span class="n">labels</span><span class="p">,</span> <span class="n">colors</span><span class="o">=</span><span class="n">colors</span><span class="p">,</span> <span class="n">autopct</span> <span class="o">=</span><span class="s2">&quot;</span><span class="si">%1.1f%%</span><span class="s2">&quot;</span><span class="p">,</span> <span class="n">shadow</span> <span class="o">=</span> <span class="kc">True</span><span class="p">,</span> <span class="n">startangle</span><span class="o">=</span><span class="mi">80</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">axis</span><span class="p">(</span><span class="s2">&quot;equal&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
XHfJ83RRAAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
