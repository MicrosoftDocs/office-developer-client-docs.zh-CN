---
title: IMAPIViewContextGetViewStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetViewStatus
api_type:
- COM
ms.assetid: 2e5ec914-7171-41ce-a6fe-78dd80ac32ff
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 992d51526c45334f6db3738e36994f4bb9c07c6e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572254"
---
# <a name="imapiviewcontextgetviewstatus"></a>IMAPIViewContext::GetViewStatus

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检索当前的查看器状态。 
  
```cpp
HRESULT GetViewStatus(
ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a>参数

 _lpulStatus_
  
> [输出]指向提供查看器的状态标志的位掩码。 可以设置以下标志：
    
VCSTATUS_CATEGORY 
  
> 在其他类别没有下一个或上一条消息。 
    
VCSTATUS_DELETE 
  
> 窗体允许要移除的消息。 
    
VCSTATUS_INTERACTIVE 
  
> 表单应显示的用户界面。 如果未设置此标志，表单应禁止显示用户界面，即使在响应通常会导致用户界面将显示动词。 
    
VCSTATUS_MODAL 
  
> 窗体是模式到查看器。 
    
VCSTATUS_NEXT 
  
> 在视图中没有下一条消息。 
    
VCSTATUS_PREV 
  
> 在视图中没有上一条消息。 
    
VCSTATUS_READONLY 
  
> 邮件是以只读模式打开。 删除、 提交，和移动操作应被禁用。 
    
VCSTATUS_UNREAD 
  
> 在视图中没有下一页或上一页未读的邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回将查看器的状态。
    
## <a name="remarks"></a>注解

表单对象调用**IMAPIViewContext::GetViewStatus**方法以确定是否在窗体视图中要激活的更多邮件或两个方向，即方向**下一步**命令在其中激活消息，请在方向**上一个**命令中激活邮件，或在两个方向。 指向_lpulStatus_参数的值用于确定是否有效的[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)VCSTATUS_NEXT 和 VCSTATUS_PREV 标志。 如果设置，但不是 VCSTATUS_READONLY 标志 VCSTATUS_DELETE 标志，然后可以使用[IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md)方法删除邮件。 
  
通常情况下，窗体禁用菜单命令和按钮如果不是有效的查看者的上下文。 查看器可以通过调用其[IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md)方法通知状态更改的表单。 
  
如果该窗体必须模式窗口的句柄传递设置 VCSTATUS_MODAL 标志早期[IMAPIForm::DoVerb](imapiform-doverb.md)呼叫中。 如果设置 VCSTATUS_MODAL，表单可以使用窗体关闭之前在其进行**DoVerb**通话的线程。 如果未设置 VCSTATUS_MODAL，窗体不应在此窗口模式，并不得使用线程。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::GetViewStatus  <br/> |MFCMAPI 此函数中实现**IMAPIViewContext::GetViewStatus**方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)
  
[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

