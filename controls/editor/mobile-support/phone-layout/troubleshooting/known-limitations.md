---
title: Known Limitations
page_title: Phone Layout Known Limitations - RadEditor
description: Check our Web Forms article about Mobile Rendering.
slug: editor/mobile-support/phone-layout/troubleshooting/known-limitations
tags: editor,support,mobile,rendering,limitations
published: True
position: 1
---

# Phone Layout Known Limitations

This help article lists the known limitations of RadEditor with **[phone layout]({%slug editor/mobile-support/phone-layout/overview%})**.

* There is a jumping of the editor when switching between HTML and Design mode or toggling the visibility of the Tool Zone in iOS browsers.

* A custom highlighting command is used for the selection in iOS (most notable) and Android browsers. The command simulates the selection highlight preserving when the Tool Zone is displayed. This resolves the *selection is lost when the current focus is changed* browser limitation. The custom highlighting command also prevents the native context menu from appearing.

* The mobile rendering of the editor requires browsers that support the Flexbox model. Therefore, the editor may look broken in older mobile browsers that do not support Flexbox.

* Right-to-left mode is not supported in the mobile rendering.

* The AjaxSpellCheck tool is not available in the mobile render mode.

## See Also

* [Phone Layout Overview]({%slug editor/mobile-support/phone-layout/overview%})
* [Known Issues]({%slug editor/mobile-support/phone-layout/troubleshooting/known-issues%})
