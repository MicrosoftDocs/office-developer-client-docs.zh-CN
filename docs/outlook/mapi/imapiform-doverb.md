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
  
请求表单执行与特定动词关联的任何任务。
  
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
  
> [in]与窗体动作之一相关联的数字。
    
 _lpViewContext_
  
> [in]指向视图上下文对象的指针。 _lpViewContext_ 参数可以是 **null**。
    
 _hwndParent_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 如果对话框或窗口不是模式对话框或窗口，_则 hwndParent_ 参数应为 null。 
    
 _lprcPosRect_
  
> [in]指向包含窗体窗口大小和位置的 Win32 [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) 结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 动词命令已成功调用。
    
OLEOBJ_S_CANNOT_DOVERB_NOW 
  
> _iVerb_ 参数表示的谓词有效，但表单无法执行当前与之关联的操作。 
    
## <a name="remarks"></a>备注

表单查看者调用 **IMAPIForm：:D oVerb** 方法，以请求表单执行与表单支持的每个动作关联的任务。 
  
每个受支持的动词都由一个数值标识，在 **iVerb** 参数中传递给 _DoVerb。_ **DoVerb 的典型** 实现包含 **一个 switch** 语句，该语句测试对表单 _的 iVerb_ 参数有效的值。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果表单查看器在  _lpViewContext_ 参数中指定视图上下文，请在你的 **DoVerb** 实现中使用它，而不是在之前对 [IMAPIForm：：SetViewContext](imapiform-setviewcontext.md) 方法的调用中传递的视图上下文。 对内部数据结构进行所需的任何更改，不要保存视图上下文。 
  
在 **DoVerb** 实现中执行以下任务： 
  
- 执行与  _iVerb_ 参数关联的特定动作所需的任何代码。 
    
- 如有必要，还原原始视图上下文。
    
- 如果传入了未知动词数字，则返回MAPI_E_NO_SUPPORT。 否则，根据所执行的任何动词的成功或失败返回结果。
    
- 关闭窗体。 您始终负责在 **DoVerb** 调用完成后关闭表单。 
    
某些动作（如 Print）对于 **DoVerb** 调用应该具有模式，也就是说，指示的操作必须在 **DoVerb** 调用返回之前完成。 
  
若要获取窗体窗口使用的 **RECT** 结构，请调用 [GetWindowRect](https://msdn.microsoft.com/library/ms633519) 函数。 
  
不要将句柄保存在  _hwndParent_ 参数中，因为尽管它通常保持有效直到 **DoVerb** 完成，但它可以在调用返回后立即销毁。
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过将  _lpViewContext_ 指向从 [IMAPIViewContext：：GetViewStatus](imapiviewcontext-getviewstatus.md) 方法返回 VCSTATUS_MODAL 标志的视图上下文实现，使非模式动词用作模式动词。 
  
有关 MAPI 中的动词功能详细信息，请参阅 [Form Verbs](form-verbs.md)。 有关在 OLE 中如何处理动作的信息，请参阅 [OLE 和数据传输](https://msdn.microsoft.com/library/ms693425%28VS.85%29.aspx)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer：：CallDoVerb  <br/> |MFCMAPI 使用 **IMAPIForm：:D oVerb** 方法调用表单上的动词。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)
  
[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[窗体动词](form-verbs.md)

