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
ms.openlocfilehash: 5b10f744e3033aab63820e4cd5e414f4c01c27cf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410614"
---
# <a name="imapiviewcontextactivatenext"></a>IMAPIViewContext::ActivateNext

**适用于**：Outlook 2013 | Outlook 2016 
  
按查看顺序激活下一条或上一封邮件。 
  
```cpp
HRESULT ActivateNext(
ULONG ulDir,
LPCRECT prcPosRect
);
```

## <a name="parameters"></a>参数

_ulDir_
  
> 实时状态标志, 提供要激活的邮件的相关信息。 有效的标志设置为:
    
  - VCDIR_CATEGORY: 查看器应激活视图的另一个类别中的邮件。 要激活的邮件为: 
        
    - 下一个视图类别中的第一条消息 (如果**** 此标志为 VCDIR_NEXT, 则为 ed)。 
        
    - 在上一视图类别中的最后一封邮件 ( **** 如果此标志为 VCDIR_PREV, 并且已展开上一个类别)。 
        
    - 在上一视图类别中的第一封邮件 ( **** 如果此标志为 VCDIR_PREV, 而以前的类别未展开)。 在这种情况下, 上一个类别会经历自动扩展。 
        
  - VCDIR_DELETE: 查看器应激活下一条或上一条消息, 因为当前邮件已被删除。 
        
  - VCDIR_MOVE: 查看器应激活下一条或上一条消息, 因为当前邮件已被移动。 
        
  - VCDIR_NEXT: 查看器应激活查看顺序中的下一封邮件。 
        
  - VCDIR_PREV: 查看器应按查看顺序激活上一封邮件。 
        
  - VCDIR_UNREAD: 查看器应激活查看顺序中的下一个或上一个未读邮件。 
    
_prcPosRect_
  
> 实时指向 Windows **RECT**结构的指针, 该结构包含要用于显示激活的消息的窗口的大小和位置。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功激活。 
    
S_FALSE 
  
> 邮件已成功激活, 但在进程中打开了另一种类型的窗体。
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIViewContext:: ActivateNext**方法以更改向用户显示的消息。 在_ulDir_参数中传递的值指示应激活的邮件, 在某些情况下, 这是为什么。 VCDIR_NEXT 和 VCDIR_PREVIOUS 标志分别对应于在视图中选择**下一个**或**上**一个命令的用户。 这些操作通常对应于在表单查看器的邮件列表中上移或下移一封邮件。 
  
VCDIR_DELETE 和 VCDIR_MOVE 标志分别由[IMAPIMessageSite::D eletemessage](imapimessagesite-deletemessage.md)和[IMAPIMessageSite:: MoveMessage](imapimessagesite-movemessage.md)方法设置。 这些方法的实现将以适当的方向调用**ActivateNext** , 然后在**ActivateNext**调用未失败时对邮件执行请求的操作。 表单查看器通常使用户能够在邮件列表中指定移动的方向。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您对[IMAPIViewContext:: ActivateNext](imapiviewcontext-activatenext.md)的实现将根据当前邮件的_ulDir_值, 在文件夹中生成下一条或上一封邮件。 在**ActivateNext**返回后, 调用[IMAPIMessageSite:: GetMessage](imapimessagesite-getmessage.md)以获取指向新激活邮件的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果**ActivateNext**返回 S_FALSE, 或者当前邮件不存在, 请执行正常关机过程, 该过程应包括调用表单的[IMAPIForm:: ShutdownForm](imapiform-shutdownform.md)方法。 如果显示的是下一条或上一条消息, 请使用_prcPosRect_参数中传递的窗口矩形来显示它。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: ActivateNext  <br/> |MFCMAPI 实现此函数中的**IMAPIViewContext:: ActivateNext**方法。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
- [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

