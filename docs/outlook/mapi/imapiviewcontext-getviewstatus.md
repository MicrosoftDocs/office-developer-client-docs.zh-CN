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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429012"
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
  
> [out]指向提供查看器状态的标记的位掩码的指针。 可以设置以下标志：
    
VCSTATUS_CATEGORY 
  
> 存在另一个类别中的下一封邮件或上一封邮件。 
    
VCSTATUS_DELETE 
  
> 窗体允许删除邮件。 
    
VCSTATUS_INTERACTIVE 
  
> 表单应显示用户界面。 如果未设置此标志，则表单应该禁止显示用户界面，即使该动作通常会导致显示用户界面。 
    
VCSTATUS_MODAL 
  
> 窗体对查看器是模式窗体。 
    
VCSTATUS_NEXT 
  
> 视图中有下一条消息。 
    
VCSTATUS_PREV 
  
> 视图中有一条以前的消息。 
    
VCSTATUS_READONLY 
  
> 邮件将在只读模式下打开。 应禁用删除、提交和移动操作。 
    
VCSTATUS_UNREAD 
  
> 视图中存在下一条或上一条未读邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回查看者的状态。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIViewContext：：GetViewStatus** 方法，以确定表单视图中是否还有更多消息需要激活，方向为：或两个方向，即 **Next** 命令激活消息的方向 **、Previous** 命令激活消息的方向或两个方向。 _lpulStatus_ 参数指向的值用于确定 VCSTATUS_NEXT 和 VCSTATUS_PREV 标志是否对 [IMAPIViewContext：：ActivateNext 有效](imapiviewcontext-activatenext.md)。 如果设置了 VCSTATUS_DELETE 标志，但没有设置 VCSTATUS_READONLY 标志，可以使用 [IMAPIMessageSite：:D eleteMessage 方法删除该](imapimessagesite-deletemessage.md) 邮件。 
  
通常，如果菜单命令和按钮与查看器的上下文无效，则表单会禁用它们。 查看者可以通过调用表单的 [IMAPIFormAdviseSink：：OnChange](imapiformadvisesink-onchange.md) 方法来提醒表单状态更改。 
  
如果VCSTATUS_MODAL必须模式化到其句柄在早期 [IMAPIForm：:D oVerb 调用中](imapiform-doverb.md) 传递的窗口，则设置该标志。 如果VCSTATUS_MODAL，窗体可以使用 **DoVerb** 调用所基于的线程，直到窗体关闭。 如果未VCSTATUS_MODAL，则表单不应是此窗口的模式，并且不得使用线程。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：GetViewStatus  <br/> |MFCMAPI 在此函数中实现 **IMAPIViewContext：：GetViewStatus** 方法。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)
  
[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

