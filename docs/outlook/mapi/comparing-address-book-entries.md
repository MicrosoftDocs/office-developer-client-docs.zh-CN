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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415353"
---
# <a name="comparing-address-book-entries"></a><span data-ttu-id="581f0-103">比较通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="581f0-103">Comparing Address Book Entries</span></span>

  
  
<span data-ttu-id="581f0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="581f0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="581f0-105">提供程序的 [IABLogon：：CompareEntryIDs](iablogon-compareentryids.md) 实现将两个提供程序对象的条目标识符进行比较。</span><span class="sxs-lookup"><span data-stu-id="581f0-105">Your provider's [IABLogon::CompareEntryIDs](iablogon-compareentryids.md) implementation compares the entry identifiers for two of your provider's objects.</span></span> <span data-ttu-id="581f0-106">MAPI 在确定两个条目标识符包含提供程序的注册 [MAPIUID](mapiuid.md)后调用此方法。</span><span class="sxs-lookup"><span data-stu-id="581f0-106">MAPI calls this method after determining that the two entry identifiers contain your provider's registered [MAPIUID](mapiuid.md).</span></span> <span data-ttu-id="581f0-107">因此 **，CompareEntryIDs** 方法无需检查 _为 lpEntryID1 和 lpEntryID2_ 参数传入的条目标识符是否属于您的提供程序。 </span><span class="sxs-lookup"><span data-stu-id="581f0-107">Therefore, your **CompareEntryIDs** method need not check that the entry identifiers passed in for the  _lpEntryID1_ and  _lpEntryID2_ parameters belong to your provider.</span></span> 
  
<span data-ttu-id="581f0-108">调用 **IABLogon：：CompareEntryIDs** 等效于检索这两个对象的 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性并直接进行比较。</span><span class="sxs-lookup"><span data-stu-id="581f0-108">Calling **IABLogon::CompareEntryIDs** is equivalent to retrieving the **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property for each of the two objects and comparing them directly.</span></span>
  
 <span data-ttu-id="581f0-109">**实现 CompareEntryIds**</span><span class="sxs-lookup"><span data-stu-id="581f0-109">**To implement CompareEntryIds**</span></span>
  
1. <span data-ttu-id="581f0-110">如果您的提供程序存储该信息，请检查传入的条目标识符的类型。</span><span class="sxs-lookup"><span data-stu-id="581f0-110">Check the type of the entry identifiers passed in if your provider stores that information.</span></span> <span data-ttu-id="581f0-111">例如，一个条目标识符可能属于邮件用户，而另一个可能属于通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="581f0-111">For example, one entry identifier might belong to a messaging user while the other might belong to a distribution list.</span></span> <span data-ttu-id="581f0-112">如果类型不匹配，将  _lpulResult_ 参数的内容设置为 FALSE 并返回。</span><span class="sxs-lookup"><span data-stu-id="581f0-112">If the types do not match, set the contents of the  _lpulResult_ parameter to FALSE and return.</span></span> 
    
2. <span data-ttu-id="581f0-113">比较两个条目标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="581f0-113">Compare the sizes of the two entry identifiers.</span></span> <span data-ttu-id="581f0-114">如果二者不相同，将  _lpulResult_ 参数的内容设置为 FALSE 并返回。</span><span class="sxs-lookup"><span data-stu-id="581f0-114">If they are not the same, set the contents of the  _lpulResult_ parameter to FALSE and return.</span></span> 
    
3. <span data-ttu-id="581f0-115">检查条目标识符的大小是否适合其类型。</span><span class="sxs-lookup"><span data-stu-id="581f0-115">Check that the size of the entry identifiers is the correct size for their type.</span></span> <span data-ttu-id="581f0-116">如果没有，将  _lpulResult_ 参数的内容设置为 FALSE，并返回错误值MAPI_E_UNKNOWN_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="581f0-116">If not, set the contents of the  _lpulResult_ parameter to FALSE and return the error value MAPI_E_UNKNOWN_ENTRYID.</span></span> 
    
4. <span data-ttu-id="581f0-117">检查条目标识符是否相同。</span><span class="sxs-lookup"><span data-stu-id="581f0-117">Check if the entry identifiers are the same.</span></span> <span data-ttu-id="581f0-118">如果二者相等，请将  _lpulResult_ 参数的内容设置为 TRUE 并返回。</span><span class="sxs-lookup"><span data-stu-id="581f0-118">If they compare equally, set the contents of the  _lpulResult_ parameter to TRUE and return.</span></span> <span data-ttu-id="581f0-119">否则，在返回之前，请设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="581f0-119">Otherwise, set it to FALSE before returning.</span></span> 
    
5. <span data-ttu-id="581f0-120">如果您的提供程序将短期条目标识符与长期标识符进行比较，则它们应进行同等比较。</span><span class="sxs-lookup"><span data-stu-id="581f0-120">If your provider is comparing a short-term entry identifier with a long-term identifier, they should compare equally.</span></span>
    

