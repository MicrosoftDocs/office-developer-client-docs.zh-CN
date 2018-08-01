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
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 9895c558af94eebebe2dacdb6f9bf674e3de6263
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776056"
---
# <a name="ipstoverride1setpersistedregistrations"></a>IPSTOVERRIDE1::SetPersistedRegistrations

**适用于**： Outlook 
  
避免进一步调用 HrTrustedPSTOverrideHandlerCallback 注册自动解锁个人文件夹 (.pst) 文件。
  
```cpp
HRESULT SetPersistedRegistrations(
  SPropValue *pmval
);
```

## <a name="parameters"></a>参数

_pmval_
  
> [in][SPropValue](spropvalue.md)结构，其中包含一个指向动态链接库 (DLL) 注册的路径。 结构具有以下特征： 
    
   - [PROP_TAG](prop_tag.md)（PT_MV_UNICODE、 PROP_ID_NULL） ulPropTag。
    
   - 设置为 null 结尾的 Unicode 字符字符串数组 MVszW value 属性。 有关详细信息，请参阅[SWStringArray](swstringarray.md)主题。 
    
> [!NOTE]
> SPropValue 存储在 PST 的内部区域中的 MAPI 属性中。 此属性为普通的 MAPI 应用程序无法访问。 
  
## <a name="return-value"></a>返回值

S_OK 
  
> 函数调用成功。
    
## <a name="remarks"></a>说明

持久化的注册可能会影响应用程序的性能，如 Outlook 和 Windows 桌面搜索，打开 Pst 的。 请考虑使用或展开持久化注册的使用情况时的性能影响。
  
> [!IMPORTANT]
> 此方法仅实现为 Unicode。 此外，它将预先失败如果任何路径数组中没有的.dll 文件扩展名。 
  
## <a name="see-also"></a>另请参阅

- [IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md) 
- [IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

