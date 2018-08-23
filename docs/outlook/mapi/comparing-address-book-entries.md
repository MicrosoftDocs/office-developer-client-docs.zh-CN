---
title: 比较通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e375367b-d107-4768-95de-00b8b9dc3511
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e5c46aed7a15ae4f48c8e4f1fe308fcb20ab3fe7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575355"
---
# <a name="comparing-address-book-entries"></a><span data-ttu-id="327f8-103">比较通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="327f8-103">Comparing Address Book Entries</span></span>

  
  
<span data-ttu-id="327f8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="327f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="327f8-105">您的提供商[IABLogon::CompareEntryIDs](iablogon-compareentryids.md)实现提供程序的对象中的两个比较的项标识符。</span><span class="sxs-lookup"><span data-stu-id="327f8-105">Your provider's [IABLogon::CompareEntryIDs](iablogon-compareentryids.md) implementation compares the entry identifiers for two of your provider's objects.</span></span> <span data-ttu-id="327f8-106">确定两个条目标识符包含您的提供商注册[MAPIUID](mapiuid.md)后，MAPI 调用此方法。</span><span class="sxs-lookup"><span data-stu-id="327f8-106">MAPI calls this method after determining that the two entry identifiers contain your provider's registered [MAPIUID](mapiuid.md).</span></span> <span data-ttu-id="327f8-107">因此，您**CompareEntryIDs**方法需要检查对于_lpEntryID1_和_lpEntryID2_参数中传递的项标识符属于您的提供商。</span><span class="sxs-lookup"><span data-stu-id="327f8-107">Therefore, your **CompareEntryIDs** method need not check that the entry identifiers passed in for the  _lpEntryID1_ and  _lpEntryID2_ parameters belong to your provider.</span></span> 
  
<span data-ttu-id="327f8-108">调用**IABLogon::CompareEntryIDs**等效于两个对象的每个检索**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性，并直接进行比较。</span><span class="sxs-lookup"><span data-stu-id="327f8-108">Calling **IABLogon::CompareEntryIDs** is equivalent to retrieving the **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property for each of the two objects and comparing them directly.</span></span>
  
 <span data-ttu-id="327f8-109">**若要实现 CompareEntryIds**</span><span class="sxs-lookup"><span data-stu-id="327f8-109">**To implement CompareEntryIds**</span></span>
  
1. <span data-ttu-id="327f8-110">检查传递中，如果您的提供商将该信息存储的项标识符的类型。</span><span class="sxs-lookup"><span data-stu-id="327f8-110">Check the type of the entry identifiers passed in if your provider stores that information.</span></span> <span data-ttu-id="327f8-111">例如，一个条目标识符可能属于邮件用户时其他可能属于通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="327f8-111">For example, one entry identifier might belong to a messaging user while the other might belong to a distribution list.</span></span> <span data-ttu-id="327f8-112">如果类型不匹配，则设置为 FALSE 和返回_lpulResult_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="327f8-112">If the types do not match, set the contents of the  _lpulResult_ parameter to FALSE and return.</span></span> 
    
2. <span data-ttu-id="327f8-113">比较两个条目标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="327f8-113">Compare the sizes of the two entry identifiers.</span></span> <span data-ttu-id="327f8-114">如果不是相同，设置为 FALSE，并返回_lpulResult_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="327f8-114">If they are not the same, set the contents of the  _lpulResult_ parameter to FALSE and return.</span></span> 
    
3. <span data-ttu-id="327f8-115">检查的项标识符的大小是正确的大小为其类型。</span><span class="sxs-lookup"><span data-stu-id="327f8-115">Check that the size of the entry identifiers is the correct size for their type.</span></span> <span data-ttu-id="327f8-116">否则，将_lpulResult_参数的内容设置为 FALSE，并返回错误值 MAPI_E_UNKNOWN_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="327f8-116">If not, set the contents of the  _lpulResult_ parameter to FALSE and return the error value MAPI_E_UNKNOWN_ENTRYID.</span></span> 
    
4. <span data-ttu-id="327f8-117">检查条目标识符是否相同。</span><span class="sxs-lookup"><span data-stu-id="327f8-117">Check if the entry identifiers are the same.</span></span> <span data-ttu-id="327f8-118">如果它们同样比较，设置为 TRUE 和返回_lpulResult_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="327f8-118">If they compare equally, set the contents of the  _lpulResult_ parameter to TRUE and return.</span></span> <span data-ttu-id="327f8-119">否则，将其设置为 FALSE 返回之前。</span><span class="sxs-lookup"><span data-stu-id="327f8-119">Otherwise, set it to FALSE before returning.</span></span> 
    
5. <span data-ttu-id="327f8-120">如果您的提供商比较具有长期标识符的短期条目标识符，他们应同样比较。</span><span class="sxs-lookup"><span data-stu-id="327f8-120">If your provider is comparing a short-term entry identifier with a long-term identifier, they should compare equally.</span></span>
    

