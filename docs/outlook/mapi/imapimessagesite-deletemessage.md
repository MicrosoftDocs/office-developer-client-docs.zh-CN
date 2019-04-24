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
  
> 实时指向视图上下文对象的指针。
    
 _prcPosRect_
  
> 实时指向包含当前窗体的窗口大小和位置的[RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx)结构的指针。 下一个显示的窗体也使用此窗口矩形。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NO_SUPPORT 
  
> 此邮件网站不支持该操作。
    
## <a name="remarks"></a>注解

form 对象调用**IMAPIMessageSite::D eletemessage**方法以删除表单当前显示的邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在返回**DeleteMessage**后, form 对象必须检查新邮件, 如果不存在, 则消除自己。 若要确定邮件**DeleteMessage**的作用是否已被删除或移动到 "**已删除邮件**" 文件夹, 窗体对象可以调用[IMAPIMessageSite:: GetSiteStatus](imapimessagesite-getsitestatus.md)方法, 以确定是否返回了 DELETE_IS_MOVE 标志。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器对**DeleteMessage**方法的实现在删除邮件后移到下一封邮件, 则该实现应调用[IMAPIViewContext:: ActivateNext](imapiviewcontext-activatenext.md)方法并在执行之前传递 VCDIR_DELETE 标志。实际删除。 如果表单查看器的**DeleteMessage**实现将已删除的邮件 (例如, 移到 "**已删除**邮件" 文件夹) 移动, 则在修改邮件时, 该实现必须保存对邮件所做的更改。 
  
**DeleteMessage**的典型实现将执行以下任务: 
  
1. 如果实现正在移动邮件, 它将调用[IPersistMessage:: Save](ipersistmessage-save.md)方法, 在_pMessage_参数中传递**null** , 在_fSameAsLoad_参数中**为 true** 。 
    
2. 它调用**IMAPIViewContext:: ActivateNext**方法, 并在_ulDir_参数中传递 VCDIR_DELETE 标志。 
    
3. 如果**ActivateNext**调用失败, 它将返回。 如果**ActivateNext**返回 S_FALSE, 它将调用[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)方法。 
    
4. 删除或移动邮件。
    
若要获取窗体窗口使用的**RECT**结构, 请调用 Windows [GetWindowRect](https://msdn.microsoft.com/library/ms633519)函数。 
  
有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer::D eletemessage  <br/> |未实现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)
  
[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)
  
[IPersistMessage::Save](ipersistmessage-save.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

