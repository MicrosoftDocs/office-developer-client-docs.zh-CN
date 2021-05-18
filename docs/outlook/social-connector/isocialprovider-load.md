---
title: ISocialProviderLoad
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6356f7bf-e3a1-4294-ad6e-df77bdd0356c
description: 初始化 OSC Outlook提供程序 (社交) 连接器。
ms.openlocfilehash: 73d14f66785417e80448f622256d0b9cb059b83c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285756"
---
# <a name="isocialproviderload"></a><span data-ttu-id="ae452-103">ISocialProvider::Load</span><span class="sxs-lookup"><span data-stu-id="ae452-103">ISocialProvider::Load</span></span>

<span data-ttu-id="ae452-104">初始化 OSC Outlook提供程序 (社交) 连接器。</span><span class="sxs-lookup"><span data-stu-id="ae452-104">Initializes the Outlook Social Connector (OSC) provider.</span></span>
  
```cpp
HRESULT _stdcall Load([in] BSTR socialProviderInterfaceVersion, [in] BSTR languageTag);
```

## <a name="parameters"></a><span data-ttu-id="ae452-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae452-105">Parameters</span></span>

<span data-ttu-id="ae452-106">_socialProviderInterfaceVersion_</span><span class="sxs-lookup"><span data-stu-id="ae452-106">_socialProviderInterfaceVersion_</span></span>
  
> <span data-ttu-id="ae452-107">[in]OSC 期望的 OSC 提供程序接口的版本。</span><span class="sxs-lookup"><span data-stu-id="ae452-107">[in] The version of the OSC provider interfaces expected by the OSC.</span></span>
    
<span data-ttu-id="ae452-108">_languageTag_</span><span class="sxs-lookup"><span data-stu-id="ae452-108">_languageTag_</span></span>
  
> <span data-ttu-id="ae452-109">[in]Internet 工程任务组 (IETF) 语言标记，由[[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)定义，表示当前 Outlook 用户界面语言。</span><span class="sxs-lookup"><span data-stu-id="ae452-109">[in] The Internet Engineering Task Force (IETF) language tag, defined by [[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt) and [[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt), that represents the current Outlook user-interface language.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ae452-110">备注</span><span class="sxs-lookup"><span data-stu-id="ae452-110">Remarks</span></span>

<span data-ttu-id="ae452-111">_socialProviderInterfaceVersion_ 参数的版本格式为 _X_。_xxxx，_ 其中 _X_ 是主要版本 _，xxxx_ 是 OSC 的次要版本。</span><span class="sxs-lookup"><span data-stu-id="ae452-111">The version format for the  _socialProviderInterfaceVersion_ parameter is  _X_. _xxxx_, where  _X_ is the major version and  _xxxx_ is the minor version of the OSC.</span></span> <span data-ttu-id="ae452-112">For Office 2013， check for the major version being 15.</span><span class="sxs-lookup"><span data-stu-id="ae452-112">For Office 2013, check for the major version being 15.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ae452-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae452-113">See also</span></span>

- [<span data-ttu-id="ae452-114">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ae452-114">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

