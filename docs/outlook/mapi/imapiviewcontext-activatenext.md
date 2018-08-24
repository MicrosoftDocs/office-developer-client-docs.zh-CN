---
title: IMAPIViewContextActivateNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.ActivateNext
api_type:
- COM
ms.assetid: 25ce90ac-526e-48a0-9edb-bd266375d4f4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6613e4168fea6536b1df873da12f2c215be515bf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588501"
---
# <a name="imapiviewcontextactivatenext"></a>IMAPIViewContext::ActivateNext

**适用于**：Outlook 2013 | Outlook 2016 
  
激活查看订单中的下一页或上一页消息。 
  
```cpp
HRESULT ActivateNext(
ULONG ulDir,
LPCRECT prcPosRect
);
```

## <a name="parameters"></a>参数

_ulDir_
  
> [in]提供有关邮件要激活的信息的状态标志。 有效的标志设置为：
    
  - VCDIR_CATEGORY： 查看器应激活另一个视图的类别中的邮件。 是要激活的消息： 
        
    - 如果此标志为与 VCDIR_NEXT**或**ed 的下一个视图类别中第一条消息。 
        
    - 展开以前的视图类别此标志是否与 VCDIR_PREV **OR**ed 和上一个类别中的最后一条消息。 
        
    - 不扩展此标志是否与 VCDIR_PREV **OR**ed 的上一视图类别和上一个类别中第一条消息。 在这种情况下上一个类别经历自动扩展。 
        
  - VCDIR_DELETE： 因为当前邮件已被删除，查看器应激活下一个或上一条消息。 
        
  - VCDIR_MOVE： 因为当前邮件已被移动，查看器应激活下一个或上一条消息。 
        
  - VCDIR_NEXT： 查看器应激活视图顺序下一条消息。 
        
  - VCDIR_PREV： 查看器应激活顺序查看以前的消息。 
        
  - VCDIR_UNREAD： 查看器应激活下一个或上一个未读的邮件视图顺序。 
    
_prcPosRect_
  
> [in]指向 Windows**矩形**结构包含的大小和位置用于显示已激活的邮件窗口。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功激活。 
    
S_FALSE 
  
> 邮件已成功激活，但过程中打开窗体的不同类型。
    
## <a name="remarks"></a>注解

表单对象调用**IMAPIViewContext::ActivateNext**方法更改向用户显示什么消息。 _UlDir_参数中传递的值表示哪些消息应该激活的并在某些情况下，原因。 VCDIR_NEXT 和 VCDIR_PREVIOUS 标志对应于用户分别在视图中，选择**下一步**或**上一步**命令。 这些操作通常对应于上移或下移一条消息中的邮件将表单查看器的列表。 
  
分别由[IMAPIMessageSite::DeleteMessage](imapimessagesite-deletemessage.md)和[IMAPIMessageSite::MoveMessage](imapimessagesite-movemessage.md)方法设置了 VCDIR_DELETE 和 VCDIR_MOVE 标志。 实现这些方法的调用**ActivateNext**相应方向，然后执行邮件上请求的操作，如果**ActivateNext**呼叫没有进行故障。 窗体查看者通常会使用户能够指定要在消息列表中移动的方向。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

在文件夹中，根据_ulDir_，当前消息的值的[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)实现使下一页或上一页消息。 **ActivateNext**返回后，调用[IMAPIMessageSite::GetMessage](imapimessagesite-getmessage.md)获取新激活的邮件的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果**ActivateNext**返回 S_FALSE，或者当前消息不存在，请执行正常关闭过程应包括调用窗体的[IMAPIForm::ShutdownForm](imapiform-shutdownform.md)方法。 如果显示下一个或上一条消息，则使用_prcPosRect_参数中传递的窗口矩形来显示它。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::ActivateNext  <br/> |MFCMAPI 此函数中实现**IMAPIViewContext::ActivateNext**方法。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
- [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

