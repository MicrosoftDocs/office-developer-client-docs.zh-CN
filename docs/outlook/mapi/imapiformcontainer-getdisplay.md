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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329426"
---
# <a name="imapiformcontainergetdisplay"></a>IMAPIFormContainer::GetDisplay

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回表单容器的显示名称。
  
```cpp
HRESULT GetDisplay(
  ULONG ulFlags,
  LPSTR FAR * pszDisplayName
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于控制返回的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _pszDisplayName_
  
> 排除指向包含表单容器的显示名称的字符串的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|FormContainerDlg  <br/> |CFormContainerDlg:: CFormContainerDlg  <br/> |MFCMAPI 在呈现 CFormContainerDlg 时使用**IMAPIFormContainer:: GetDisplay**方法获取表单容器的名称。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

