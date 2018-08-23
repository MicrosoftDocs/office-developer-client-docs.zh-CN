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
ms.openlocfilehash: 4b05baf1f819a821da3496cc63c2b2980894efd7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575712"
---
# <a name="hrgetgalfromemsmdbuid"></a><span data-ttu-id="393ec-103">HrGetGALFromEmsmdbUID</span><span class="sxs-lookup"><span data-stu-id="393ec-103">HrGetGALFromEmsmdbUID</span></span>

  
  
<span data-ttu-id="393ec-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="393ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="393ec-105">返回标识_pEmsmdbUID_的 Exchange 服务的全局通讯簿条目标识符。</span><span class="sxs-lookup"><span data-stu-id="393ec-105">Returns the entry identifier of the global address book for the Exchange service identified by  _pEmsmdbUID_.</span></span> <span data-ttu-id="393ec-106">应使用[MAPIFreeBuffer](mapifreebuffer.md)释放返回的项标识符。</span><span class="sxs-lookup"><span data-stu-id="393ec-106">The returned entry identifier should be freed using [MAPIFreeBuffer](mapifreebuffer.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="393ec-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="393ec-107">Header file:</span></span>  <br/> |<span data-ttu-id="393ec-108">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="393ec-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="393ec-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="393ec-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="393ec-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="393ec-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="393ec-111">调用：</span><span class="sxs-lookup"><span data-stu-id="393ec-111">Called by:</span></span>  <br/> |<span data-ttu-id="393ec-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="393ec-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrGetGALFromEmsmdbUID(
  LPMAPISESSION pSess,
  LPADRBOOK lpAdrBook,
  const MAPIUID * pEmsmdbUID,
  ULONG * lpcbeid,
  LPENTRYID * lppeid
);
```

## <a name="parameters"></a><span data-ttu-id="393ec-113">参数</span><span class="sxs-lookup"><span data-stu-id="393ec-113">Parameters</span></span>

 <span data-ttu-id="393ec-114">_pSess_</span><span class="sxs-lookup"><span data-stu-id="393ec-114">_pSess_</span></span>
  
> <span data-ttu-id="393ec-115">[in]登录 IMAPISession。</span><span class="sxs-lookup"><span data-stu-id="393ec-115">[in] The logged on IMAPISession.</span></span> <span data-ttu-id="393ec-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="393ec-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="393ec-117">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="393ec-117">_pAddrBook_</span></span>
  
> <span data-ttu-id="393ec-118">[in]通讯簿用于打开的项标识符。</span><span class="sxs-lookup"><span data-stu-id="393ec-118">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="393ec-119">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="393ec-119">It cannot be NULL.</span></span>
    
 <span data-ttu-id="393ec-120">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="393ec-120">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="393ec-121">[in]标识要检索的 Exchange 服务 GAL **emsmdbUID**指向的指针。</span><span class="sxs-lookup"><span data-stu-id="393ec-121">[in] A pointer to an **emsmdbUID** that identifies the GAL of the Exchange Service to be retrieved.</span></span> <span data-ttu-id="393ec-122">如果_pEmsmdbUID_为 NULL 或零 UID，此函数获取旧 GAL 的 Exchange 服务。</span><span class="sxs-lookup"><span data-stu-id="393ec-122">If  _pEmsmdbUID_ is NULL or the zero UID, this function gets the legacy GAL of the Exchange Service.</span></span> 
    
 <span data-ttu-id="393ec-123">_lpcbeid_</span><span class="sxs-lookup"><span data-stu-id="393ec-123">_lpcbeid_</span></span>
  
> <span data-ttu-id="393ec-124">[输出]一个指向全局地址列表的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="393ec-124">[out] A pointer to the byte count of the entry identifier of the global address list.</span></span>
    
 <span data-ttu-id="393ec-125">_lppeid_</span><span class="sxs-lookup"><span data-stu-id="393ec-125">_lppeid_</span></span>
  
> <span data-ttu-id="393ec-126">[输出]一个指向全局地址列表的项标识符。</span><span class="sxs-lookup"><span data-stu-id="393ec-126">[out] A pointer to the entry identifier of the global address list.</span></span> <span data-ttu-id="393ec-127">应使用[MAPIFreeBuffer](mapifreebuffer.md)释放这。</span><span class="sxs-lookup"><span data-stu-id="393ec-127">This should be freed using [MAPIFreeBuffer](mapifreebuffer.md).</span></span>
    

