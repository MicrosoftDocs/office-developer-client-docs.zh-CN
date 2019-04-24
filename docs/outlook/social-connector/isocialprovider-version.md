---
title: ISocialProviderVersion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: dfc92878-ab8b-4721-aee8-997c56a8e45b
description: 返回一个 string 类型的值, 该值代表此社交网络提供程序的版本号。
ms.openlocfilehash: 0749b8fb83a11328233442b79e1f9de50076effe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285383"
---
# <a name="isocialproviderversion"></a><span data-ttu-id="3c02d-103">ISocialProvider::Version</span><span class="sxs-lookup"><span data-stu-id="3c02d-103">ISocialProvider::Version</span></span>

<span data-ttu-id="3c02d-104">返回一个 string 类型的值, 该值代表此社交网络提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="3c02d-104">Returns a string that represents the version number of the provider for this social network.</span></span> 
  
```cpp
[propget] HRESULT _stdcall Version([out, retval] BSTR* Version);
```

## <a name="property-value"></a><span data-ttu-id="3c02d-105">属性值</span><span class="sxs-lookup"><span data-stu-id="3c02d-105">Property value</span></span>

<span data-ttu-id="3c02d-106">一个包含提供程序版本号的字符串。</span><span class="sxs-lookup"><span data-stu-id="3c02d-106">A string that contains the version number of the provider.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3c02d-107">注解</span><span class="sxs-lookup"><span data-stu-id="3c02d-107">Remarks</span></span>

<span data-ttu-id="3c02d-108">版本字符串应使用_MajorVersion_。</span><span class="sxs-lookup"><span data-stu-id="3c02d-108">The version string should use the  _MajorVersion_.</span></span> <span data-ttu-id="3c02d-109">_MinorVersion_格式 (例如, 1.4730)。</span><span class="sxs-lookup"><span data-stu-id="3c02d-109">_MinorVersion_ format (for example, 1.4730).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3c02d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c02d-110">See also</span></span>

- [<span data-ttu-id="3c02d-111">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3c02d-111">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

