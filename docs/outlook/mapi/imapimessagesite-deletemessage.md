---
title: IMAPIMessageSiteDeleteMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.DeleteMessage
api_type:
- COM
ms.assetid: 09955996-b904-4c0d-8ba5-954a8875c055
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7b2761e20444c51d08380aee01c41eee797733eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321411"
---
# <a name="imapimessagesitedeletemessage"></a>IMAPIMessageSite::DeleteMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除当前邮件。
  
```cpp
HRESULT DeleteMessage(
  LPMAPIVIEWCONTEXT pViewContext,
  LPCRECT prcPosRect
);
```

## <a name="parameters"></a>参数

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

表单对象调用 **IMAPIMessageSite：:D eleteMessage** 方法以删除表单当前显示的消息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

返回 **DeleteMessage** 之后，form 对象必须检查新邮件，然后在不存在邮件时自行消除。 若要确定对 **DeleteMessage** 操作的邮件是已删除还是移动到"已删除邮件"文件夹，表单对象可以调用 [IMAPIMessageSite：：GetSiteStatus](imapimessagesite-getsitestatus.md)方法以确定是否返回 DELETE_IS_MOVE 标志。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器的 **DeleteMessage** 方法实现在删除邮件后移至下一条消息，则实现应调用 [IMAPIViewContext：：ActivateNext](imapiviewcontext-activatenext.md) 方法，并传递 VCDIR_DELETE 标志，然后再执行实际删除。 如果表单查看器的 **DeleteMessage** 实现将已删除的邮件 (例如移动到"已删除邮件"文件夹) ，则实现必须保存对邮件所做的更改（如果邮件已修改）。 
  
**DeleteMessage 的典型** 实现执行以下任务： 
  
1. 如果实现移动消息，它将调用 [IPersistMessage：：Save](ipersistmessage-save.md)方法，在 _pMessage_ 参数中传递 **null，** 在 _fSameAsLoad_ 参数中传递 **true。** 
    
2. 它调用 **IMAPIViewContext：：ActivateNext** 方法，在  _ulDir_ VCDIR_DELETE传递该标记。 
    
3. 如果 **ActivateNext 调用** 失败，它将返回。 如果 **ActivateNext** 返回 S_FALSE，它将调用 [IPersistMessage：：HandsOffMessage](ipersistmessage-handsoffmessage.md) 方法。 
    
4. 它会删除或移动邮件。
    
若要获取窗体的窗口使用的 **RECT** 结构，请调用 Windows [GetWindowRect](https://msdn.microsoft.com/library/ms633519)函数。 
  
有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：:D eleteMessage  <br/> |未实现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)
  
[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)
  
[IPersistMessage::Save](ipersistmessage-save.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

