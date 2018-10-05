---
title: ISocialProviderLoad
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6356f7bf-e3a1-4294-ad6e-df77bdd0356c
description: 初始化 Outlook Social Connector (OSC) 提供程序。
ms.openlocfilehash: 73d14f66785417e80448f622256d0b9cb059b83c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385828"
---
# <a name="isocialproviderload"></a><span data-ttu-id="f3b37-103">ISocialProvider::Load</span><span class="sxs-lookup"><span data-stu-id="f3b37-103">ISocialProvider::Load</span></span>

<span data-ttu-id="f3b37-104">初始化 Outlook Social Connector (OSC) 提供程序。</span><span class="sxs-lookup"><span data-stu-id="f3b37-104">Initializes the Outlook Social Connector (OSC) provider.</span></span>
  
```cpp
HRESULT _stdcall Load([in] BSTR socialProviderInterfaceVersion, [in] BSTR languageTag);
```

## <a name="parameters"></a><span data-ttu-id="f3b37-105">参数</span><span class="sxs-lookup"><span data-stu-id="f3b37-105">Parameters</span></span>

<span data-ttu-id="f3b37-106">_socialProviderInterfaceVersion_</span><span class="sxs-lookup"><span data-stu-id="f3b37-106">_socialProviderInterfaceVersion_</span></span>
  
> <span data-ttu-id="f3b37-107">[in]所需的 OSC OSC 提供程序接口的版本。</span><span class="sxs-lookup"><span data-stu-id="f3b37-107">[in] The version of the OSC provider interfaces expected by the OSC.</span></span>
    
<span data-ttu-id="f3b37-108">_languageTag_</span><span class="sxs-lookup"><span data-stu-id="f3b37-108">_languageTag_</span></span>
  
> <span data-ttu-id="f3b37-109">[in]Internet 工程任务组 (IETF) 语言标记，由[[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)，值，该值代表当前 Outlook 用户界面语言。</span><span class="sxs-lookup"><span data-stu-id="f3b37-109">[in] The Internet Engineering Task Force (IETF) language tag, defined by [[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt) and [[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt), that represents the current Outlook user-interface language.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f3b37-110">说明</span><span class="sxs-lookup"><span data-stu-id="f3b37-110">Remarks</span></span>

<span data-ttu-id="f3b37-111">_SocialProviderInterfaceVersion_参数的版本格式为_X_。_格式_，其中_X_是主要版本和_格式_是 OSC 的次要版本。</span><span class="sxs-lookup"><span data-stu-id="f3b37-111">The version format for the  _socialProviderInterfaceVersion_ parameter is  _X_. _xxxx_, where  _X_ is the major version and  _xxxx_ is the minor version of the OSC.</span></span> <span data-ttu-id="f3b37-112">Office 2013 的检查正在 15 的主要版本。</span><span class="sxs-lookup"><span data-stu-id="f3b37-112">For Office 2013, check for the major version being 15.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f3b37-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3b37-113">See also</span></span>

- [<span data-ttu-id="f3b37-114">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f3b37-114">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

