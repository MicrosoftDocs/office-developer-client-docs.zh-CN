---
title: IPSTOVERRIDE1SetPersistedRegistrations
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDE1.SetPersistedRegistrations
api_type:
- COM
ms.assetid: 5f4b62db-a759-41a2-9bea-29fc04b2962b
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 6583765d4df7c7bfae9e7a62606beaa857874954
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408346"
---
# <a name="ipstoverride1setpersistedregistrations"></a>IPSTOVERRIDE1::SetPersistedRegistrations

**适用于**：Outlook 2013 | Outlook 2016 
  
为自动解锁注册个人文件夹 (.pst) 文件, 以避免对 HrTrustedPSTOverrideHandlerCallback 的进一步调用。
  
```cpp
HRESULT SetPersistedRegistrations(
  SPropValue *pmval
);
```

## <a name="parameters"></a>参数

_pmval_
  
> 实时一个[SPropValue](spropvalue.md)结构, 其中包含指向要注册的动态链接库 (DLL) 的路径的指针。 结构具有以下特征: 
    
   - [PROP_TAG](prop_tag.md)(PT_MV_UNICODE, PROP_ID_NULL) 的 ulPropTag。
    
   - 一个 MVszW 值属性, 该属性设置为以 null 结尾的 Unicode 字符串的数组。 有关详细信息, 请参阅[SWStringArray](swstringarray.md)主题。 
    
> [!NOTE]
> SPropValue 存储在 PST 的内部范围内的 MAPI 属性中。 普通 MAPI 应用程序无法访问此属性。 
  
## <a name="return-value"></a>返回值

S_OK 
  
> 函数调用成功。
    
## <a name="remarks"></a>说明

持久化注册可能会对打开 pst 的应用程序 (如 Outlook 和 Windows 桌面搜索) 的性能产生不利影响。 在使用或扩展持久化注册的使用情况时, 请考虑性能影响。
  
> [!IMPORTANT]
> 仅为 Unicode 实现此方法。 此外, 如果数组中的任何路径的文件扩展名均不为 .dll, 则 preemptively 将失败。 
  
## <a name="see-also"></a>另请参阅

- [IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md) 
- [IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

