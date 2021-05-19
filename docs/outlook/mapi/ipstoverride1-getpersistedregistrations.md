---
title: IPSTOVERRIDE1GetPersistedRegistrations
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDE1.GetPersistedRegistrations
api_type:
- COM
ms.assetid: 027092f0-f2d6-49e8-a8d0-8926824953a2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 822b4164737aa6010ccce108b544410104ac023d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415129"
---
# <a name="ipstoverride1getpersistedregistrations"></a>IPSTOVERRIDE1::GetPersistedRegistrations

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索个人文件夹的注册列表 (.pst) 文件。
  
```cpp
HRESULT GetPersistedRegistration(SPropValue **ppmval);
```

## <a name="parameters"></a>参数

 _ppmval_
  
> [in]指向指向 [SPropValue 结构的指针的](spropvalue.md) 指针。 此结构的 ulPropTag 成员的类型为 PT_MV_UNICODE，MVszW 值成员将为以 null 终止的 Unicode 字符串数组。 这些字符串是一直保留注册的 DLL 的路径。 
    
> [!NOTE]
> 未实现对 ANSI 的 .pst 支持。 
  
## <a name="return-value"></a>返回值

S_OK 
  
> 函数调用成功。
    
## <a name="see-also"></a>另请参阅



[IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md)
  
[IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

