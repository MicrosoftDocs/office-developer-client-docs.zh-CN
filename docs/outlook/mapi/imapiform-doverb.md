---
title: IMAPIFormDoVerb
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.DoVerb
api_type:
- COM
ms.assetid: 8b582571-b448-4476-91d9-4cc94dbec710
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 60a8c89afe0d70a1737c6ce694c66359fd6aae4f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398092"
---
# <a name="imapiformdoverb"></a>IMAPIForm::DoVerb

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
请求窗体执行任何任务它将与特定动词。
  
```cpp
HRESULT DoVerb(
  LONG iVerb,
  LPMAPIVIEWCONTEXT lpViewContext,
  ULONG_PTR hwndParent,
  LPCRECT lprcPosRect
);
```

## <a name="parameters"></a>参数

 _iVerb_
  
> [in]使用一个窗体的动作相关联的编号。
    
 _lpViewContext_
  
> [in]指向视图上下文对象的指针。 _LpViewContext_参数可以为**null**。
    
 _hwndParent_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 如果对话框或窗口不是模式， _hwndParent_参数应为**null** 。 
    
 _lprcPosRect_
  
> [in]指向 Win32[矩形](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx)结构，其中包含的大小和窗体的窗口的位置。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功调用动词。
    
OLEOBJ_S_CANNOT_DOVERB_NOW 
  
> 由_iVerb_参数表示的动作有效，但表单无法执行与其当前关联的操作。 
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIForm::DoVerb**方法以请求窗体执行它将与该窗体支持每个动作相关联的任务。 
  
每个受支持的动作由传递给**DoVerb** _iVerb_参数中的数值标识。 **DoVerb**的典型实现包含**switch**语句的测试可用于窗体的_iVerb_参数的值。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器_lpViewContext_参数中指定了视图上下文，则**DoVerb**实现而不是以前[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)方法调用中传递的视图上下文中使用它。 进行任何更改是向内部数据结构所必需的且不保存视图上下文。 
  
**DoVerb**实现中执行以下任务： 
  
- 执行任何代码是必要的特定谓词的与_iVerb_参数相关联。 
    
- 如有必要，还原原始视图上下文。
    
- 如果中传递了未知的动词数，返回 MAPI_E_NO_SUPPORT。 否则，返回基于是成功还是失败的执行任何操作的结果。
    
- 关闭窗体。 它始终是您有责任**DoVerb**调用完成后关闭表单。 
    
某些谓词，如打印，应为模式相对于**DoVerb**呼叫 — 即，指示的操作必须**DoVerb**调用返回之前完成。 
  
若要获取使用窗体的窗口的**矩形**结构，请调用[GetWindowRect](https://msdn.microsoft.com/library/ms633519)函数。 
  
因为，但它通常保持有效**DoVerb**完成之后，它可以销毁立即的调用返回时，不要_hwndParent_参数中保存句柄。
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过从其[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)方法返回 VCSTATUS_MODAL 标志视图上下文实现指向_lpViewContext_用作模式谓词的非模式动词。 
  
有关谓词 MAPI 中的详细信息，请参阅[窗体动词](form-verbs.md)。 有关在 OLE 动作的处理方式的详细信息，请参阅[OLE 和数据传输](https://msdn.microsoft.com/library/ms693425%28VS.85%29.aspx)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::CallDoVerb  <br/> |MFCMAPI 使用**IMAPIForm::DoVerb**方法调用窗体上的动词。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)
  
[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[表单谓词](form-verbs.md)

