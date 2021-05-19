---
title: IMAPIFormContainerGetDisplay
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.GetDisplay
api_type:
- COM
ms.assetid: 6829e273-4a75-4278-b58a-ae7543e075ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 994041d050df56fd3fa3c0e599542e05a202ad65
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416130"
---
# <a name="imapiformcontainergetdisplay"></a>IMAPIFormContainer::GetDisplay

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回显示名称容器的容器。
  
```cpp
HRESULT GetDisplay(
  ULONG ulFlags,
  LPSTR FAR * pszDisplayName
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制返回的字符串类型的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _pszDisplayName_
  
> [out]指向包含表单容器显示名称字符串的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FormContainerDlg.cpp  <br/> |CFormContainerDlg：：CFormContainerDlg  <br/> |MFCMAPI 在呈现 **CFormContainerDlg 时，使用 IMAPIFormContainer：：GetDisplay** 方法获取表单容器的名称。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

