---
title: HrGetGALFromEmsmdbUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9b824e70-ed9a-490c-b777-8902a793fece
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b9a31fec93ec7fafc4d1565d63e4bc427ba4050e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347829"
---
# <a name="hrgetgalfromemsmdbuid"></a><span data-ttu-id="8dae6-103">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="8dae6-103">HrGetGALFromEmsmdbUID</span></span>

  
  
<span data-ttu-id="8dae6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8dae6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8dae6-105">返回由_pEmsmdbUID_标识的 Exchange 服务的全局通讯簿的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8dae6-105">Returns the entry identifier of the global address book for the Exchange service identified by  _pEmsmdbUID_.</span></span> <span data-ttu-id="8dae6-106">应使用[MAPIFreeBuffer](mapifreebuffer.md)释放返回的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8dae6-106">The returned entry identifier should be freed using [MAPIFreeBuffer](mapifreebuffer.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8dae6-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="8dae6-107">Header file:</span></span>  <br/> |<span data-ttu-id="8dae6-108">abhelp</span><span class="sxs-lookup"><span data-stu-id="8dae6-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="8dae6-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="8dae6-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="8dae6-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="8dae6-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="8dae6-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="8dae6-111">Called by:</span></span>  <br/> |<span data-ttu-id="8dae6-112">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="8dae6-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrGetGALFromEmsmdbUID(
  LPMAPISESSION pSess,
  LPADRBOOK lpAdrBook,
  const MAPIUID * pEmsmdbUID,
  ULONG * lpcbeid,
  LPENTRYID * lppeid
);
```

## <a name="parameters"></a><span data-ttu-id="8dae6-113">参数</span><span class="sxs-lookup"><span data-stu-id="8dae6-113">Parameters</span></span>

 <span data-ttu-id="8dae6-114">_pSess_</span><span class="sxs-lookup"><span data-stu-id="8dae6-114">_pSess_</span></span>
  
> <span data-ttu-id="8dae6-115">实时登录的 IMAPISession。</span><span class="sxs-lookup"><span data-stu-id="8dae6-115">[in] The logged on IMAPISession.</span></span> <span data-ttu-id="8dae6-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8dae6-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="8dae6-117">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="8dae6-117">_pAddrBook_</span></span>
  
> <span data-ttu-id="8dae6-118">实时用于打开条目标识符的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="8dae6-118">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="8dae6-119">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8dae6-119">It cannot be NULL.</span></span>
    
 <span data-ttu-id="8dae6-120">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="8dae6-120">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="8dae6-121">实时指向标识要检索的 Exchange 服务的 GAL 的**emsmdbUID**的指针。</span><span class="sxs-lookup"><span data-stu-id="8dae6-121">[in] A pointer to an **emsmdbUID** that identifies the GAL of the Exchange Service to be retrieved.</span></span> <span data-ttu-id="8dae6-122">如果_pEmsmdbUID_为 NULL 或 0 UID, 则此函数将获取 Exchange 服务的旧版 GAL。</span><span class="sxs-lookup"><span data-stu-id="8dae6-122">If  _pEmsmdbUID_ is NULL or the zero UID, this function gets the legacy GAL of the Exchange Service.</span></span> 
    
 <span data-ttu-id="8dae6-123">_lpcbeid_</span><span class="sxs-lookup"><span data-stu-id="8dae6-123">_lpcbeid_</span></span>
  
> <span data-ttu-id="8dae6-124">排除一个指针, 指向全局地址列表的条目标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="8dae6-124">[out] A pointer to the byte count of the entry identifier of the global address list.</span></span>
    
 <span data-ttu-id="8dae6-125">_lppeid_</span><span class="sxs-lookup"><span data-stu-id="8dae6-125">_lppeid_</span></span>
  
> <span data-ttu-id="8dae6-126">排除指向全局地址列表的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="8dae6-126">[out] A pointer to the entry identifier of the global address list.</span></span> <span data-ttu-id="8dae6-127">应使用[MAPIFreeBuffer](mapifreebuffer.md)对此进行释放。</span><span class="sxs-lookup"><span data-stu-id="8dae6-127">This should be freed using [MAPIFreeBuffer](mapifreebuffer.md).</span></span>
    

