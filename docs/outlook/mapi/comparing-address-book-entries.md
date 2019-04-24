---
title: 比较通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e375367b-d107-4768-95de-00b8b9dc3511
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6ccd7a55c195b45b1fa83db6180efeacd41b968d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335530"
---
# <a name="comparing-address-book-entries"></a><span data-ttu-id="73820-103">比较通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="73820-103">Comparing Address Book Entries</span></span>

  
  
<span data-ttu-id="73820-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="73820-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="73820-105">提供程序的[IABLogon:: CompareEntryIDs](iablogon-compareentryids.md)实现将比较两个提供程序对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="73820-105">Your provider's [IABLogon::CompareEntryIDs](iablogon-compareentryids.md) implementation compares the entry identifiers for two of your provider's objects.</span></span> <span data-ttu-id="73820-106">MAPI 在确定这两个条目标识符是否包含提供程序的注册[MAPIUID](mapiuid.md)之后, 将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="73820-106">MAPI calls this method after determining that the two entry identifiers contain your provider's registered [MAPIUID](mapiuid.md).</span></span> <span data-ttu-id="73820-107">因此, **CompareEntryIDs**方法无需检查为_lpEntryID1_和_lpEntryID2_参数传入的条目标识符是否属于您的提供程序。</span><span class="sxs-lookup"><span data-stu-id="73820-107">Therefore, your **CompareEntryIDs** method need not check that the entry identifiers passed in for the  _lpEntryID1_ and  _lpEntryID2_ parameters belong to your provider.</span></span> 
  
<span data-ttu-id="73820-108">调用**IABLogon:: CompareEntryIDs**等效于检索两个对象中的每个对象的**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性, 并直接对它们进行比较。</span><span class="sxs-lookup"><span data-stu-id="73820-108">Calling **IABLogon::CompareEntryIDs** is equivalent to retrieving the **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property for each of the two objects and comparing them directly.</span></span>
  
 <span data-ttu-id="73820-109">**实现 CompareEntryIds**</span><span class="sxs-lookup"><span data-stu-id="73820-109">**To implement CompareEntryIds**</span></span>
  
1. <span data-ttu-id="73820-110">如果提供程序存储了这些信息, 请检查传入的条目标识符的类型。</span><span class="sxs-lookup"><span data-stu-id="73820-110">Check the type of the entry identifiers passed in if your provider stores that information.</span></span> <span data-ttu-id="73820-111">例如, 一个条目标识符可能属于邮件用户, 而另一个条目标识符可能属于通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="73820-111">For example, one entry identifier might belong to a messaging user while the other might belong to a distribution list.</span></span> <span data-ttu-id="73820-112">如果类型不匹配, 请将_lpulResult_参数的内容设置为 FALSE 并返回。</span><span class="sxs-lookup"><span data-stu-id="73820-112">If the types do not match, set the contents of the  _lpulResult_ parameter to FALSE and return.</span></span> 
    
2. <span data-ttu-id="73820-113">比较两个条目标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="73820-113">Compare the sizes of the two entry identifiers.</span></span> <span data-ttu-id="73820-114">如果它们不相同, 请将_lpulResult_参数的内容设置为 FALSE 并返回。</span><span class="sxs-lookup"><span data-stu-id="73820-114">If they are not the same, set the contents of the  _lpulResult_ parameter to FALSE and return.</span></span> 
    
3. <span data-ttu-id="73820-115">检查条目标识符的大小是否为其类型的正确大小。</span><span class="sxs-lookup"><span data-stu-id="73820-115">Check that the size of the entry identifiers is the correct size for their type.</span></span> <span data-ttu-id="73820-116">如果不是, 请将_lpulResult_参数的内容设置为 FALSE, 并返回错误值 MAPI_E_UNKNOWN_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="73820-116">If not, set the contents of the  _lpulResult_ parameter to FALSE and return the error value MAPI_E_UNKNOWN_ENTRYID.</span></span> 
    
4. <span data-ttu-id="73820-117">检查条目标识符是否相同。</span><span class="sxs-lookup"><span data-stu-id="73820-117">Check if the entry identifiers are the same.</span></span> <span data-ttu-id="73820-118">如果比较相等, 请将_lpulResult_参数的内容设置为 TRUE 并返回。</span><span class="sxs-lookup"><span data-stu-id="73820-118">If they compare equally, set the contents of the  _lpulResult_ parameter to TRUE and return.</span></span> <span data-ttu-id="73820-119">否则, 在返回之前将其设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="73820-119">Otherwise, set it to FALSE before returning.</span></span> 
    
5. <span data-ttu-id="73820-120">如果提供程序正在将短期条目标识符与长期标识符进行比较, 则这些标识符应相等比较。</span><span class="sxs-lookup"><span data-stu-id="73820-120">If your provider is comparing a short-term entry identifier with a long-term identifier, they should compare equally.</span></span>
    

