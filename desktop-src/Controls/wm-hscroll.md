---
title: WM\_HSCROLL message
description: The WM\_HSCROLL message is sent to a window when a scroll event occurs in the window's standard horizontal scroll bar.
ms.assetid: '197e522f-defd-4356-8521-5b5dfda596da'
keywords: ["WM_HSCROLL message Windows Controls"]
topic_type:
- apiref
api_name:
- WM_HSCROLL
api_location:
- Winuser.h
api_type:
- HeaderDef
---

# WM\_HSCROLL message

The **WM\_HSCROLL** message is sent to a window when a scroll event occurs in the window's standard horizontal scroll bar. This message is also sent to the owner of a horizontal scroll bar control when a scroll event occurs in the control.

A window receives this message through its [*WindowProc*](https://msdn.microsoft.com/library/windows/desktop/ms633573) function.


```C++
WM_HSCROLL

    WPARAM wParam
    LPARAM lParam; 
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

The [**HIWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632657) specifies the current position of the scroll box if the [**LOWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632659) is SB\_THUMBPOSITION or SB\_THUMBTRACK; otherwise, this word is not used.

The [**LOWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632659) specifies a scroll bar value that indicates the user's scrolling request. This word can be one of the following values.



| Value                                                                                                                                                                  | Meaning                                                                                                                                                                                                                   |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="SB_ENDSCROLL"></span><span id="sb_endscroll"></span><dl> <dt>**SB\_ENDSCROLL**</dt> </dl>             | Ends scroll.<br/>                                                                                                                                                                                                   |
| <span id="SB_LEFT"></span><span id="sb_left"></span><dl> <dt>**SB\_LEFT**</dt> </dl>                            | Scrolls to the upper left.<br/>                                                                                                                                                                                     |
| <span id="SB_RIGHT"></span><span id="sb_right"></span><dl> <dt>**SB\_RIGHT**</dt> </dl>                         | Scrolls to the lower right.<br/>                                                                                                                                                                                    |
| <span id="SB_LINELEFT"></span><span id="sb_lineleft"></span><dl> <dt>**SB\_LINELEFT**</dt> </dl>                | Scrolls left by one unit.<br/>                                                                                                                                                                                      |
| <span id="SB_LINERIGHT"></span><span id="sb_lineright"></span><dl> <dt>**SB\_LINERIGHT**</dt> </dl>             | Scrolls right by one unit.<br/>                                                                                                                                                                                     |
| <span id="SB_PAGELEFT"></span><span id="sb_pageleft"></span><dl> <dt>**SB\_PAGELEFT**</dt> </dl>                | Scrolls left by the width of the window.<br/>                                                                                                                                                                       |
| <span id="SB_PAGERIGHT"></span><span id="sb_pageright"></span><dl> <dt>**SB\_PAGERIGHT**</dt> </dl>             | Scrolls right by the width of the window.<br/>                                                                                                                                                                      |
| <span id="SB_THUMBPOSITION"></span><span id="sb_thumbposition"></span><dl> <dt>**SB\_THUMBPOSITION**</dt> </dl> | The user has dragged the scroll box (thumb) and released the mouse button. The [**HIWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632657) indicates the position of the scroll box at the end of the drag operation.<br/>                          |
| <span id="SB_THUMBTRACK"></span><span id="sb_thumbtrack"></span><dl> <dt>**SB\_THUMBTRACK**</dt> </dl>          | The user is dragging the scroll box. This message is sent repeatedly until the user releases the mouse button. The [**HIWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632657) indicates the position that the scroll box has been dragged to.<br/> |



�

</dd> <dt>

*lParam* 
</dt> <dd>

If the message is sent by a scroll bar control, this parameter is the handle to the scroll bar control. If the message is sent by a standard scroll bar, this parameter is **NULL**.

</dd> </dl>

## Return value

If an application processes this message, it should return zero.

## Remarks

The SB\_THUMBTRACK request code is typically used by applications that provide feedback as the user drags the scroll box.

If an application scrolls the content of the window, it must also reset the position of the scroll box by using the [**SetScrollPos**](setscrollpos.md) function.

Note that the **WM\_HSCROLL** message carries only 16 bits of scroll box position data. Thus, applications that rely solely on **WM\_HSCROLL** (and [**WM\_VSCROLL**](wm-vscroll.md)) for scroll position data have a practical maximum position value of 65,535.

However, because the [**SetScrollInfo**](setscrollinfo.md), [**SetScrollPos**](setscrollpos.md), [**SetScrollRange**](setscrollrange.md), [**GetScrollInfo**](getscrollinfo.md), [**GetScrollPos**](getscrollpos.md), and [**GetScrollRange**](getscrollrange.md) functions support 32-bit scroll bar position data, there is a way to circumvent the 16-bit barrier of the **WM\_HSCROLL** and [**WM\_VSCROLL**](wm-vscroll.md) messages. See **GetScrollInfo** for a description of the technique.

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�Vista \[desktop apps only\]<br/>                                                           |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Winuser.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[**GetScrollInfo**](getscrollinfo.md)
</dt> <dt>

[**GetScrollPos**](getscrollpos.md)
</dt> <dt>

[**GetScrollRange**](getscrollrange.md)
</dt> <dt>

[**SetScrollInfo**](setscrollinfo.md)
</dt> <dt>

[**SetScrollPos**](setscrollpos.md)
</dt> <dt>

[**SetScrollRange**](setscrollrange.md)
</dt> <dt>

[**WM\_HSCROLL (trackbar)**](wm-hscroll--trackbar-.md)
</dt> <dt>

[**WM\_VSCROLL**](wm-vscroll.md)
</dt> </dl>

�

�




