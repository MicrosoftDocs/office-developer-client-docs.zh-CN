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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 548ec33e39e181aba8a72b5325f3f426b9d51762
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575866"
---
# <a name="ipstoverride1getpersistedregistrations"></a>IPSTOVERRIDE1::GetPersistedRegistrations

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检索的登记个人文件夹 (.pst) 文件的列表。
  
```cpp
HRESULT GetPersistedRegistration(SPropValue **ppmval);
```

## <a name="parameters"></a>参数

 _ppmval_
  
> [in]指向[SPropValue](spropvalue.md)结构的指针的指针。 此结构的 ulPropTag 成员的类型 PT_MV_UNICODE，并且 MVszW 值成员都是 null 结尾的 Unicode 字符串数组。 这些字符串是对已经为其保持了注册的 Dll 的路径。 
    
> [!NOTE]
> 未实现 ANSI.pst 支持。 
  
## <a name="return-value"></a>返回值

S_OK 
  
> 函数调用成功。
    
## <a name="see-also"></a>另请参阅



[IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md)
  
[IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

