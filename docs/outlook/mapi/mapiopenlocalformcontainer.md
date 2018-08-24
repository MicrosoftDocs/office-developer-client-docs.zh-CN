---
title: MAPIOpenLocalFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIOpenLocalFormContainer
api_type:
- COM
ms.assetid: 1c53170f-03a6-4a05-913e-de8eeadea692
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87696ceea96bd2f51bfe5a0b062499946179c8b3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582558"
---
# <a name="mapiopenlocalformcontainer"></a>MAPIOpenLocalFormContainer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回到本地表单库的接口指针。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
MAPIOpenLocalFormContainer(
  LPMAPIFORMCONTAINER FAR * ppfcnt
);
```

## <a name="parameters"></a>参数

 _ppfcnt_
  
> [输出]指向本地窗体库接口的指针的指针。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

第三方安装程序可以使用指针返回到该接口到库中安装应用程序特定的表单，而无需程序事先登录到 MAPI。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnMAPIOpenLocalFormContainer  <br/> |MFCMAPI 使用**MAPIOpenLocalFormContainer**方法打开要在新窗口中呈现的本地窗体容器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

