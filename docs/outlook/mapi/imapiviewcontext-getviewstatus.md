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
ms.openlocfilehash: bb8699746b3f4207ee70edd4e56d0ec6041beac2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351175"
---
# <a name="imapiviewcontextgetviewstatus"></a>IMAPIViewContext::GetViewStatus

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索当前查看器状态。 
  
```cpp
HRESULT GetViewStatus(
ULONG FAR * lpulStatus
);
```

## <a name="parameters"></a>参数

 _lpulStatus_
  
> 排除指向提供查看器状态的标志的位掩码的指针。 可以设置以下标志:
    
VCSTATUS_CATEGORY 
  
> 另一个类别中有下一个或上一个邮件。 
    
VCSTATUS_DELETE 
  
> 该窗体允许删除邮件。 
    
VCSTATUS_INTERACTIVE 
  
> 表单应显示用户界面。 如果未设置此标志, 则表单应禁止显示用户界面, 即使是响应通常会导致显示用户界面的动作也是如此。 
    
VCSTATUS_MODAL 
  
> 窗体是查看器的模式。 
    
VCSTATUS_NEXT 
  
> 视图中存在下一条消息。 
    
VCSTATUS_PREV 
  
> 视图中有上一封邮件。 
    
VCSTATUS_READONLY 
  
> 将在只读模式下打开邮件。 应禁用删除、提交和移动操作。 
    
VCSTATUS_UNREAD 
  
> 视图中存在下一个或上一个未读邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回查看器的状态。
    
## <a name="remarks"></a>注解

表单对象调用**IMAPIViewContext:: GetViewStatus**方法, 以确定在一种或两种方向的 "窗体" 视图中是否有更多的要激活的邮件, 这些方向是在 "**下一步**" 命令激活邮件的方向, 在上一个命令激活邮件的方向, 或在两个方向**上**激活邮件的方向。 _lpulStatus_参数所指向的值用于确定 VCSTATUS_NEXT 和 VCSTATUS_PREV 标志对[IMAPIViewContext:: ActivateNext](imapiviewcontext-activatenext.md)是否有效。 如果设置了 VCSTATUS_DELETE 标志, 而不是 VCSTATUS_READONLY 标志, 则可以使用[IMAPIMessageSite::D eletemessage](imapimessagesite-deletemessage.md)方法删除邮件。 
  
通常, 如果窗体对查看者的上下文无效, 则会禁用菜单命令和按钮。 查看者可以通过调用其[IMAPIFormAdviseSink:: OnChange](imapiformadvisesink-onchange.md)方法, 将窗体的状态更改警告到状态更改。 
  
如果窗体必须是在之前的 IMAPIForm 中传递的句柄所在窗口的模式, 则设置 VCSTATUS_MODAL 标志[::D overb](imapiform-doverb.md)调用。 如果设置了 VCSTATUS_MODAL, 则表单可以使用在其上进行**DoVerb**调用的线程, 直到窗体关闭。 如果未设置 VCSTATUS_MODAL, 则该窗体不应为此窗口的模式, 并且不得使用该线程。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: GetViewStatus  <br/> |MFCMAPI 实现此函数中的**IMAPIViewContext:: GetViewStatus**方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)
  
[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

