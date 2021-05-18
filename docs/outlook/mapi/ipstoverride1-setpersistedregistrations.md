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
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: 6583765d4df7c7bfae9e7a62606beaa857874954
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408346"
---
# <a name="ipstoverride1setpersistedregistrations"></a>IPSTOVERRIDE1::SetPersistedRegistrations

**适用于**：Outlook 2013 | Outlook 2016 
  
将个人文件夹 (.pst) 文件进行自动解锁，以避免进一步调用 HrTrustedPSTOverrideHandlerCallback。
  
```cpp
HRESULT SetPersistedRegistrations(
  SPropValue *pmval
);
```

## <a name="parameters"></a>参数

_pmval_
  
> [in]一 [个 SPropValue](spropvalue.md) 结构，包含指向动态链接库路径的指针 (DLL) 进行注册。 结构具有以下特征： 
    
   - 一个 ulPropTag [](prop_tag.md) PROP_TAG (PT_MV_UNICODE PROP_ID_NULL) 。
    
   - 一个 MVszW 值属性，设置为以 null 结束的 Unicode 字符串数组。 有关详细信息，请参阅 [SWStringArray](swstringarray.md) 主题。 
    
> [!NOTE]
> SPropValue 存储在 PST 内部范围的 MAPI 属性中。 普通 MAPI 应用程序无法访问此属性。 
  
## <a name="return-value"></a>返回值

S_OK 
  
> 函数调用成功。
    
## <a name="remarks"></a>备注

保留的注册可能会对打开 PST 的应用程序（如桌面Outlook Windows搜索）的性能产生不利影响。 在使用或扩展持续注册的使用时，请考虑性能影响。
  
> [!IMPORTANT]
> 此方法仅为 Unicode 实现。 此外，如果数组中的任一路径的文件扩展名没有扩展名.dll。 
  
## <a name="see-also"></a>另请参阅

- [IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md) 
- [IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

