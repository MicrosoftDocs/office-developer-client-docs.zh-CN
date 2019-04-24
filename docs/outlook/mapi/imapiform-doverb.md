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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329454"
---
# <a name="imapiformdoverb"></a>IMAPIForm::DoVerb

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
请求表单执行与特定谓词相关联的任何任务。
  
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
  
> 实时与窗体的一个谓词相关联的数字。
    
 _lpViewContext_
  
> 实时指向视图上下文对象的指针。 _lpViewContext_参数可以为**null**。
    
 _hwndParent_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 如果对话框或窗口不模式, 则_hwndParent_参数应为**null** 。 
    
 _lprcPosRect_
  
> 实时指向 Win32 [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx)结构的指针, 该结构包含窗体的窗口的大小和位置。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功调用谓词。
    
OLEOBJ_S_CANNOT_DOVERB_NOW 
  
> 由_iVerb_参数表示的谓词是有效的, 但该窗体无法执行当前与之关联的操作。 
    
## <a name="remarks"></a>注解

表单查看器调用**IMAPIForm::D overb**方法, 以请求表单执行与表单支持的每个谓词相关联的任务。 
  
每个受支持的谓词都通过一个数值标识, 并传递给_iVerb_参数中的**DoVerb** 。 **DoVerb**的典型实现包含一个**switch**语句, 用于测试对窗体的_iVerb_参数有效的值。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器在_lpViewContext_参数中指定了视图上下文, 请在**DoVerb**实现中使用它, 而不是在之前调用[IMAPIForm:: SetViewContext](imapiform-setviewcontext.md)方法时传递的视图上下文。 对内部数据结构进行任何所需的更改, 并且不保存视图上下文。 
  
在您的**DoVerb**实现中执行以下任务: 
  
- 执行与_iVerb_参数关联的特定谓词所需的任何代码。 
    
- 如有必要, 请还原原始的视图上下文。
    
- 如果传入了未知动词号码, 则返回 MAPI_E_NO_SUPPORT。 否则, 根据执行的任何动作的成功或失败返回结果。
    
- 关闭窗体。 在**DoVerb**调用完成后, 始终负责关闭窗体。 
    
某些谓词 (如 Print) 应是有关**DoVerb**调用的模式, 也就是说, 在**DoVerb**调用返回之前, 必须完成指示的操作。 
  
若要获取窗体窗口使用的**RECT**结构, 请调用[GetWindowRect](https://msdn.microsoft.com/library/ms633519)函数。 
  
请勿将句柄保存在_hwndParent_参数中, 因为尽管它通常在**DoVerb**完成之前一直有效, 但它可以在调用返回时立即销毁。
  
## <a name="notes-to-callers"></a>给调用方的说明

通过将_lpViewContext_指向从其[IMAPIViewContext:: GetViewStatus](imapiviewcontext-getviewstatus.md)方法返回 VCSTATUS_MODAL 标志的视图上下文实现, 可以使非模式谓词充当模式谓词。 
  
有关 MAPI 中的动词的详细信息, 请参阅[表单谓词](form-verbs.md)。 有关如何在 ole 中处理谓词的详细信息, 请参阅[ole and Data Transfer](https://msdn.microsoft.com/library/ms693425%28VS.85%29.aspx)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer  <br/> |CMyMAPIFormViewer:: CallDoVerb  <br/> |MFCMAPI 使用**IMAPIForm::D overb**方法调用窗体上的谓词。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)
  
[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[表单谓词](form-verbs.md)

