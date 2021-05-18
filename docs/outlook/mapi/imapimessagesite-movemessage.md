---
title: IMAPIMessageSiteMoveMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.MoveMessage
api_type:
- COM
ms.assetid: cd4d7b11-fad0-4f05-a99e-9567abcab45c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c68e4fbda661a119416918a2c35d1780f1deccda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321362"
---
# <a name="imapimessagesitemovemessage"></a>IMAPIMessageSite::MoveMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将当前邮件移动到文件夹。
  
```cpp
HRESULT MoveMessage(
  LPFOLDER pFolderDestination,
  LPMAPIVIEWCONTEXT pViewContext,
  LPCRECT prcPosRect
);
```

## <a name="parameters"></a>参数

 _pFolderDestination_
  
> [in]指向要移动邮件的文件夹的指针。
    
 _pViewContext_
  
> [in]指向视图上下文对象的指针。
    
 _prcPosRect_
  
> [in]指向包含当前窗体的窗口大小和位置的 [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) 结构的指针。 显示的下一个窗体也使用此窗口矩形。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_NO_SUPPORT 
  
> 此消息网站不支持该操作。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIMessageSite：：MoveMessage** 方法将当前邮件移动到新文件夹。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

表单查看器的 **MoveMessage** 实现必须调用 [IMAPIViewContext：：ActivateNext](imapiviewcontext-activatenext.md) 方法，并传递 VCDIR_MOVE 标志，然后才能将邮件实际移动到新文件夹。 若要获取窗体的窗口使用的 **RECT** 结构，请调用 Windows [GetWindowRect](https://msdn.microsoft.com/library/ms633519)函数。 
  
有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

返回 **MoveMessage** 后，表单必须检查当前邮件，然后在不存在邮件时自行消除。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：MoveMessage  <br/> |未实现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

