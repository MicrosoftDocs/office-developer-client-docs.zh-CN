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
ms.openlocfilehash: 6ed73cd683f1668900a76f7b8c48494952e9fc14
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573346"
---
# <a name="imapimessagesitedeletemessage"></a>IMAPIMessageSite::DeleteMessage

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]指向[矩形](http://msdn.microsoft.com/en-us/library/dd162897%28VS.85%29.aspx)结构，其中包含当前表单的窗口的大小和位置的指针。 显示的下一个窗体也使用此窗口矩形。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_SUPPORT 
  
> 该操作不受此消息网站。
    
## <a name="remarks"></a>注解

Form 对象调用**IMAPIMessageSite::DeleteMessage**方法删除当前显示窗体的邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**DeleteMessage**返回时，以下表单对象必须检查新邮件，然后关闭本身，如果不存在。 若要确定是否**DeleteMessage**作用于邮件已被删除或移动到**已删除邮件**文件夹，form 对象可以调用[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)方法以确定是否返回 DELETE_IS_MOVE 标志。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果后将删除在一条消息， **DeleteMessage**方法的表单查看器的实现将移至下一条消息，实现应调用[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)方法，并将 VCDIR_DELETE 标志传递执行之前实际删除。 如果**DeleteMessage**表单查看器的实现移动 （例如，到**已删除邮件**文件夹中） 的已删除的消息，实现必须到邮件保存更改，如果邮件的修改。 
  
**DeleteMessage**的典型实现执行以下任务： 
  
1. 如果实现在移动邮件，它会调用[IPersistMessage::Save](ipersistmessage-save.md)方法，传递**null** _pMessage_参数中和**true** _fSameAsLoad_参数。 
    
2. 它调用**IMAPIViewContext::ActivateNext**方法， _ulDir_参数中传递 VCDIR_DELETE 标志。 
    
3. 如果**ActivateNext**调用将失败，则返回。 如果**ActivateNext**返回 S_FALSE，它会调用[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)方法。 
    
4. 它删除，或将邮件移动。
    
若要获取使用窗体的窗口的**矩形**结构，请调用 Windows [GetWindowRect](http://msdn.microsoft.com/en-us/library/ms633519)函数。 
  
有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::DeleteMessage  <br/> |未实现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)
  
[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)
  
[IPersistMessage::Save](ipersistmessage-save.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

