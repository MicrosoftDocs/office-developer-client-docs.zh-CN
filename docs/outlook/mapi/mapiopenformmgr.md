---
title: MAPIOpenFormMgr
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIOpenFormMgr
api_type:
- COM
ms.assetid: 5b624954-d975-4d5e-84d7-74e096ac30af
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de0c1181450c536dffd5a84242c17bd1dd612566
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418048"
---
# <a name="mapiopenformmgr"></a>MAPIOpenFormMgr

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开现有会话上下文中的表单库提供程序对象上的 [IMAPIFormMgr](imapiformmgriunknown.md) 接口。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
MAPIOpenFormMgr(
  LPMAPISESSION pSession,
  LPMAPIFORMMGR FAR * ppmgr
);
```

## <a name="parameters"></a>参数

 _pSession_
  
> [in]指向客户端应用程序使用的会话的指针。
    
 _ppmgr_
  
> [out]指向返回的 **IMAPIFormMgr 接口的** 指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

在客户端应用程序调用 **MAPIOpenFormMgr** 函数后，大多数后续的表单相关交互都通过表单库提供程序或表单库提供程序返回的接口发生。 **IMAPIFormMgr** 接口允许客户端使用消息处理程序，并执行消息类和表单库之间的解决方案。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp 打开表单管理器，以便选择表单。  <br/> |CMainDlg：：OnSelectForm  <br/> |MFCMAPI 使用 **MAPIOpenFormMgr** 方法打开表单管理器，以便选择表单。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

