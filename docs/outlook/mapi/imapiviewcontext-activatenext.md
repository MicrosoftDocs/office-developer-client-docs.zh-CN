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
  
按查看顺序激活下一封邮件或上一封邮件。 
  
```cpp
HRESULT ActivateNext(
ULONG ulDir,
LPCRECT prcPosRect
);
```

## <a name="parameters"></a>参数

_ulDir_
  
> [in]状态标志，提供有关要激活的邮件的信息。 有效标志设置包括：
    
  - VCDIR_CATEGORY：查看者应激活视图其他类别中的邮件。 要激活的邮件为： 
        
    - 如果此标志是 OR，则下一视图类别中的第一封邮件VCDIR_NEXT。 
        
    - 上一视图类别中的最后一封邮件（如果此标志是 **OR** ed，VCDIR_PREV并且上一个类别已展开）。 
        
    - 如果上一视图类别中的第一封邮件是 **OR，** 则此标志VCDIR_PREV且上一个类别未展开。 在这种情况下，前一类别执行自动扩展。 
        
  - VCDIR_DELETE：查看者应激活下一封邮件或上一封邮件，因为当前邮件已删除。 
        
  - VCDIR_MOVE：查看者应激活下一封邮件或上一封邮件，因为当前邮件已移动。 
        
  - VCDIR_NEXT：查看者应按查看顺序激活下一封邮件。 
        
  - VCDIR_PREV：查看者应按查看顺序激活上一封邮件。 
        
  - VCDIR_UNREAD：查看者应按查看顺序激活下一条或上一条未读邮件。 
    
_prcPosRect_
  
> [in]指向一Windows RECT 结构的指针，该 **RECT** 结构包含用于显示已激活消息的窗口的大小和位置。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功激活。 
    
S_FALSE 
  
> 邮件已成功激活，但过程中打开了不同类型的表单。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIViewContext：：ActivateNext** 方法来更改向用户显示的消息。 ulDir 参数  _中_ 传递的值指示应激活哪些邮件，在某些情况下，指示原因。 "VCDIR_NEXT"和"VCDIR_PREVIOUS"标志分别对应于在视图中选择"**下** 一步"或"上一步"命令的用户。 这些操作通常对应于在窗体查看器的邮件列表中上移或下移一封邮件。 
  
VCDIR_DELETE 和 VCDIR_MOVE 标志分别由 [IMAPIMessageSite：:D eleteMessage](imapimessagesite-deletemessage.md) 和 [IMAPIMessageSite：：MoveMessage](imapimessagesite-movemessage.md) 方法设置。 这些方法的实现使用适当的方向调用 **ActivateNext，** 然后在 **ActivateNext** 调用未失败时对邮件执行请求的操作。 窗体查看器通常允许用户指定在邮件列表中移动的方向。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

[IMAPIViewContext：：ActivateNext](imapiviewcontext-activatenext.md)的实现在文件夹中创建下一个或上一封邮件，具体取决于 _ulDir_ 的值，即当前邮件。 **ActivateNext** 返回后，调用 [IMAPIMessageSite：：GetMessage](imapimessagesite-getmessage.md)获取指向新激活的消息的指针。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 **ActivateNext** S_FALSE，或者如果当前消息不存在，请执行正常的关闭过程，该过程应包括调用表单的 [IMAPIForm：：ShutdownForm](imapiform-shutdownform.md) 方法。 如果显示下一条或上一条消息，请使用  _在 prcPosRect_ 参数中传递的窗口矩形来显示它。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：ActivateNext  <br/> |MFCMAPI 在此函数中实现 **IMAPIViewContext：：ActivateNext** 方法。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
- [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)
- [MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

