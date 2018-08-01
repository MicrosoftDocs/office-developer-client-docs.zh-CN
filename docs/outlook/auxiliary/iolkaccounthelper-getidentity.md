---
title: IOlkAccountHelperGetIdentity
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea8b8f02-959f-cd71-9cfe-5ebdf4bae2bc
description: 获取帐户的配置文件名称。
ms.openlocfilehash: 81417282faa9ba0e7ec99990ac78045b54752acb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774337"
---
# <a name="iolkaccounthelpergetidentity"></a><span data-ttu-id="a619a-103">IOlkAccountHelper::GetIdentity</span><span class="sxs-lookup"><span data-stu-id="a619a-103">IOlkAccountHelper::GetIdentity</span></span>

<span data-ttu-id="a619a-104">获取帐户的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="a619a-104">Gets the profile name of an account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="a619a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="a619a-105">Quick info</span></span>

<span data-ttu-id="a619a-106">请参阅[IOlkAccountHelper](iolkaccounthelper.md)。</span><span class="sxs-lookup"><span data-stu-id="a619a-106">See [IOlkAccountHelper](iolkaccounthelper.md).</span></span>
  
```cpp
HRESULT IOlkAccountHelper::GetIdentity (  
    LPWSTR pwszIdentity, 
    DWORD *pcch 
);
```

## <a name="parameters"></a><span data-ttu-id="a619a-107">参数</span><span class="sxs-lookup"><span data-stu-id="a619a-107">Parameters</span></span>

<span data-ttu-id="a619a-108">_pwszIdentity_</span><span class="sxs-lookup"><span data-stu-id="a619a-108">_pwszIdentity_</span></span>
  
> <span data-ttu-id="a619a-109">[in][输出]配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a619a-109">[in][out] The profile name.</span></span>
    
<span data-ttu-id="a619a-110">_pcch_</span><span class="sxs-lookup"><span data-stu-id="a619a-110">_pcch_</span></span>
  
> <span data-ttu-id="a619a-111">[in][输出]时调用此方法，都包含_pwszIdentity_已分配的大小 （以字符数）。</span><span class="sxs-lookup"><span data-stu-id="a619a-111">[in] [out] Upon calling this method, contains the size (in number of characters) of  _pwszIdentity_ that has been allocated.</span></span> <span data-ttu-id="a619a-112">返回时，包含的实际长度，包括 0 终止，返回的配置文件名称字符。</span><span class="sxs-lookup"><span data-stu-id="a619a-112">Upon return, contains the actual length, including the 0-terminating character, of the returned profile name.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="a619a-113">返回值</span><span class="sxs-lookup"><span data-stu-id="a619a-113">Return values</span></span>

|<span data-ttu-id="a619a-114">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="a619a-114">**HRESULT**</span></span>|<span data-ttu-id="a619a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a619a-115">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a619a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a619a-116">S_OK</span></span>  <br/> |<span data-ttu-id="a619a-117">调用成功。</span><span class="sxs-lookup"><span data-stu-id="a619a-117">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="a619a-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a619a-118">E_OUTOFMEMORY</span></span>  <br/> |<span data-ttu-id="a619a-119">返回的配置文件名称的长度超过_pwszIdentity_的大小。</span><span class="sxs-lookup"><span data-stu-id="a619a-119">The returned profile name is longer than the size of  _pwszIdentity_.</span></span>  <br/> |
|<span data-ttu-id="a619a-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a619a-120">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="a619a-121">_pcch_为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a619a-121">_pcch_ is NULL.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a619a-122">说明</span><span class="sxs-lookup"><span data-stu-id="a619a-122">Remarks</span></span>

<span data-ttu-id="a619a-123">如果_pwszIdentity_太小，若要保留的配置文件名称，将不会设置返回时，并且_pcch_将指向_pwszIdentity_所需的大小。</span><span class="sxs-lookup"><span data-stu-id="a619a-123">If  _pwszIdentity_ is too small to hold the profile name, it will not be set on return, and  _pcch_ will point to the size required for  _pwszIdentity_.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a619a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a619a-124">See also</span></span>

- [<span data-ttu-id="a619a-125">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="a619a-125">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="a619a-126">PidTagProfileName</span><span class="sxs-lookup"><span data-stu-id="a619a-126">PidTagProfileName</span></span>](http://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx)

