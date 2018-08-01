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
ms.openlocfilehash: 0451d8635848705ef912b9a575d6390898251f4f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775466"
---
# <a name="imapimessagesitemovemessage"></a>IMAPIMessageSite::MoveMessage

  
  
**适用于**： Outlook 
  
将当前邮件移动到文件夹中。
  
```cpp
HRESULT MoveMessage(
  LPFOLDER pFolderDestination,
  LPMAPIVIEWCONTEXT pViewContext,
  LPCRECT prcPosRect
);
```

## <a name="parameters"></a>参数

 _pFolderDestination_
  
> [in]一个指向邮件将被移动其中的文件夹。
    
 _pViewContext_
  
> [in]指向视图上下文对象的指针。
    
 _prcPosRect_
  
> [in]指向[矩形](http://msdn.microsoft.com/en-us/library/dd162897%28VS.85%29.aspx)结构，其中包含当前表单的窗口的大小和位置的指针。 显示的下一个窗体也使用此窗口矩形。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_SUPPORT 
  
> 该操作不受此消息网站。
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIMessageSite::MoveMessage**方法将当前邮件移至新文件夹。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

表单查看器的实现**MoveMessage**必须调用传递 VCDIR_MOVE 标志，实际上将邮件移至新文件夹前的[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)方法。 若要获取使用窗体的窗口的**矩形**结构，请调用 Windows [GetWindowRect](http://msdn.microsoft.com/en-us/library/ms633519)函数。 
  
有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。
  
## <a name="notes-to-callers"></a>给调用方的说明

**MoveMessage**返回时，以下窗体必须检查当前消息，然后关闭本身，如果不存在。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::MoveMessage  <br/> |未实现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 表单接口](mapi-form-interfaces.md)

