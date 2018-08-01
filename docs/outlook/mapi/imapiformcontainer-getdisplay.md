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
ms.openlocfilehash: 0f9826dab72968055604c5bb9f8f537facc5618e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775406"
---
# <a name="imapiformcontainergetdisplay"></a>IMAPIFormContainer::GetDisplay

  
  
**适用于**： Outlook 
  
返回一个窗体容器的显示名称。
  
```cpp
HRESULT GetDisplay(
  ULONG ulFlags,
  LPSTR FAR * pszDisplayName
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志的控制返回的字符串的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，该字符串是以 ANSI 格式。
    
 _pszDisplayName_
  
> [输出]一个指向包含窗体容器的显示名称的字符串。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|FormContainerDlg.cpp  <br/> |CFormContainerDlg::CFormContainerDlg  <br/> |MFCMAPI 使用**IMAPIFormContainer::GetDisplay**方法来呈现 CFormContainerDlg 时获取窗体容器的名称。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

