---
title: IMAPIFormContainerRemoveForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.RemoveForm
api_type:
- COM
ms.assetid: 7f851ce8-bd01-4ea5-86e0-e44323cc0aab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e53c0cbd9946ff04516594a7ce99fdc2daf4ff4d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355740"
---
# <a name="imapiformcontainerremoveform"></a>IMAPIFormContainer::RemoveForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从表单容器中删除特定的窗体。
  
```cpp
HRESULT RemoveForm(
  LPCSTR szMessageClass
);
```

## <a name="parameters"></a>参数

 _szMessageClass_
  
> 实时一个字符串, 用于命名要从表单容器中删除的表单的邮件类。 邮件类名称始终为 ANSI 字符串, 决不能为 Unicode。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NOT_FOUND 
  
> 在_szMessageClass_参数中传递的邮件类与表单容器中任何表单的邮件类都不匹配。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FormContainerDlg  <br/> |CFormContainerDlg:: OnDeleteSelectedItem  <br/> |MFCMAPI 使用**IMAPIFormContainer:: RemoveForm**方法从窗体容器中删除窗体。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

