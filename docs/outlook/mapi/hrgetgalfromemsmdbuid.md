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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439105"
---
# <a name="hrgetgalfromemsmdbuid"></a><span data-ttu-id="6e46d-103">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="6e46d-103">HrGetGALFromEmsmdbUID</span></span>

  
  
<span data-ttu-id="6e46d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e46d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e46d-105">返回由 _pEmsmdbUID_ 标识的 Exchange 的全局通讯簿的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="6e46d-105">Returns the entry identifier of the global address book for the Exchange service identified by  _pEmsmdbUID_.</span></span> <span data-ttu-id="6e46d-106">应该使用 [MAPIFreeBuffer](mapifreebuffer.md)释放返回的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="6e46d-106">The returned entry identifier should be freed using [MAPIFreeBuffer](mapifreebuffer.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6e46d-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6e46d-107">Header file:</span></span>  <br/> |<span data-ttu-id="6e46d-108">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="6e46d-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="6e46d-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="6e46d-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="6e46d-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="6e46d-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="6e46d-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="6e46d-111">Called by:</span></span>  <br/> |<span data-ttu-id="6e46d-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="6e46d-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrGetGALFromEmsmdbUID(
  LPMAPISESSION pSess,
  LPADRBOOK lpAdrBook,
  const MAPIUID * pEmsmdbUID,
  ULONG * lpcbeid,
  LPENTRYID * lppeid
);
```

## <a name="parameters"></a><span data-ttu-id="6e46d-113">参数</span><span class="sxs-lookup"><span data-stu-id="6e46d-113">Parameters</span></span>

 <span data-ttu-id="6e46d-114">_pSess_</span><span class="sxs-lookup"><span data-stu-id="6e46d-114">_pSess_</span></span>
  
> <span data-ttu-id="6e46d-115">[in]登录的 IMAPISession。</span><span class="sxs-lookup"><span data-stu-id="6e46d-115">[in] The logged on IMAPISession.</span></span> <span data-ttu-id="6e46d-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6e46d-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="6e46d-117">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="6e46d-117">_pAddrBook_</span></span>
  
> <span data-ttu-id="6e46d-118">[in]用于打开条目标识符的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="6e46d-118">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="6e46d-119">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6e46d-119">It cannot be NULL.</span></span>
    
 <span data-ttu-id="6e46d-120">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="6e46d-120">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="6e46d-121">[in]指向标识要检索的 Exchange 服务的 GAL 的 **emsmdbUID** 的指针。</span><span class="sxs-lookup"><span data-stu-id="6e46d-121">[in] A pointer to an **emsmdbUID** that identifies the GAL of the Exchange Service to be retrieved.</span></span> <span data-ttu-id="6e46d-122">如果 _pEmsmdbUID_ 为 NULL 或零 UID，则此函数将获取 Exchange Service 的旧 GAL。</span><span class="sxs-lookup"><span data-stu-id="6e46d-122">If  _pEmsmdbUID_ is NULL or the zero UID, this function gets the legacy GAL of the Exchange Service.</span></span> 
    
 <span data-ttu-id="6e46d-123">_lpc一d_</span><span class="sxs-lookup"><span data-stu-id="6e46d-123">_lpcbeid_</span></span>
  
> <span data-ttu-id="6e46d-124">[out]指向全局地址列表条目标识符的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="6e46d-124">[out] A pointer to the byte count of the entry identifier of the global address list.</span></span>
    
 <span data-ttu-id="6e46d-125">_lppeid_</span><span class="sxs-lookup"><span data-stu-id="6e46d-125">_lppeid_</span></span>
  
> <span data-ttu-id="6e46d-126">[out]指向全局地址列表的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="6e46d-126">[out] A pointer to the entry identifier of the global address list.</span></span> <span data-ttu-id="6e46d-127">这应该使用 [MAPIFreeBuffer 释放](mapifreebuffer.md)。</span><span class="sxs-lookup"><span data-stu-id="6e46d-127">This should be freed using [MAPIFreeBuffer](mapifreebuffer.md).</span></span>
    

