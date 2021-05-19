---
title: IAddrBookSetSearchPath
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.SetSearchPath
api_type:
- COM
ms.assetid: fbff82de-77d3-411e-a30c-a37cefdd92fc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8611249207811446ae47f056486ec498bf1e7eab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426203"
---
# <a name="iaddrbooksetsearchpath"></a><span data-ttu-id="78829-103">IAddrBook::SetSearchPath</span><span class="sxs-lookup"><span data-stu-id="78829-103">IAddrBook::SetSearchPath</span></span>

  
  
<span data-ttu-id="78829-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="78829-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="78829-105">设置配置文件中用于名称解析过程的新搜索路径。</span><span class="sxs-lookup"><span data-stu-id="78829-105">Sets a new search path in the profile that is used for the name resolution process.</span></span> 
  
```cpp
HRESULT SetSearchPath(
  ULONG ulFlags,
  LPSRowSet lpSearchPath
);
```

## <a name="parameters"></a><span data-ttu-id="78829-106">参数</span><span class="sxs-lookup"><span data-stu-id="78829-106">Parameters</span></span>

 <span data-ttu-id="78829-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="78829-107">_ulFlags_</span></span>
  
> <span data-ttu-id="78829-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="78829-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="78829-109">_lpSearchPath_</span><span class="sxs-lookup"><span data-stu-id="78829-109">_lpSearchPath_</span></span>
  
> <span data-ttu-id="78829-110">[in]指向用于保留 [搜索路径的 SRowSet](srowset.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="78829-110">[in] A pointer to the [SRowSet](srowset.md) structure used to hold the search path.</span></span> <span data-ttu-id="78829-111">**SRowSet** 中每个 **aRow** 成员的第一个属性必须PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="78829-111">The first property for each **aRow** member in **SRowSet** must be **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="78829-112">返回值</span><span class="sxs-lookup"><span data-stu-id="78829-112">Return value</span></span>

<span data-ttu-id="78829-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="78829-113">S_OK</span></span> 
  
> <span data-ttu-id="78829-114">已成功设置搜索路径。</span><span class="sxs-lookup"><span data-stu-id="78829-114">The search path was successfully set.</span></span>
    
<span data-ttu-id="78829-115">MAPI_E_MISSING_REQUIRED_COLUMN</span><span class="sxs-lookup"><span data-stu-id="78829-115">MAPI_E_MISSING_REQUIRED_COLUMN</span></span> 
  
> <span data-ttu-id="78829-116">**SRowSet** 结构中描述的容器之一 **不包括其** PR_ENTRYID 属性。</span><span class="sxs-lookup"><span data-stu-id="78829-116">One of the containers described in the **SRowSet** structure did not include its **PR_ENTRYID** property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="78829-117">备注</span><span class="sxs-lookup"><span data-stu-id="78829-117">Remarks</span></span>

<span data-ttu-id="78829-118">客户端和服务提供商调用 **SetSearchPath** 方法来保存对容器搜索顺序所做的更改，该搜索顺序用于使用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 方法解析名称。</span><span class="sxs-lookup"><span data-stu-id="78829-118">Clients and service providers call the **SetSearchPath** method to save changes that were made to the container search order that is used to resolve names with the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method.</span></span> <span data-ttu-id="78829-119">搜索路径在会话的实例之间保存。</span><span class="sxs-lookup"><span data-stu-id="78829-119">The search path is saved between instances of a session.</span></span> 
  
<span data-ttu-id="78829-120">客户端和提供程序不需要调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来永久更改搜索路径。</span><span class="sxs-lookup"><span data-stu-id="78829-120">Clients and providers do not have to call the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to make the search path changes permanent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="78829-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78829-121">See also</span></span>



[<span data-ttu-id="78829-122">IAddrBook::GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="78829-122">IAddrBook::GetDefaultDir</span></span>](iaddrbook-getdefaultdir.md)
  
[<span data-ttu-id="78829-123">IAddrBook::GetPAB</span><span class="sxs-lookup"><span data-stu-id="78829-123">IAddrBook::GetPAB</span></span>](iaddrbook-getpab.md)
  
[<span data-ttu-id="78829-124">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="78829-124">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="78829-125">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="78829-125">PidTagContainerFlags Canonical Property</span></span>](pidtagcontainerflags-canonical-property.md)
  
[<span data-ttu-id="78829-126">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="78829-126">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

