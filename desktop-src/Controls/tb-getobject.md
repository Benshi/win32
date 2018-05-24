---
title: TB\_GETOBJECT message
description: Retrieves the IDropTarget for a toolbar control.
ms.assetid: 'b26394ea-6f0f-4084-956d-f9166cc54b76'
keywords: ["TB_GETOBJECT message Windows Controls"]
topic_type:
- apiref
api_name:
- TB_GETOBJECT
api_location:
- Commctrl.h
api_type:
- HeaderDef
---

# TB\_GETOBJECT message

Retrieves the [**IDropTarget**](https://msdn.microsoft.com/library/windows/desktop/ms679679) for a toolbar control.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

Identifier of the interface being requested. This value must point to **IID\_IDropTarget**.

</dd> <dt>

*lParam* 
</dt> <dd>

Address that receives the interface pointer. If an error occurs, a **NULL** pointer is placed in this address.

</dd> </dl>

## Return value

Returns an **HRESULT** value indicating success or failure of the operation.

## Remarks

The toolbar's [**IDropTarget**](https://msdn.microsoft.com/library/windows/desktop/ms679679) is used by the toolbar when objects are dragged over or dropped onto it.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Commctrl.h</dt> </dl> |



�

�




