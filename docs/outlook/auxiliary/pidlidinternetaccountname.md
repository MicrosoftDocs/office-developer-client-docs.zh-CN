---
title: PidLidInternetAccountName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5acca047-ff2a-716c-8dd4-b676fce1a3cf
description: 返回发送邮件的帐户的显示名称。
ms.openlocfilehash: 223bc5bbd485426676376d94875274613ff59685
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774431"
---
# <a name="pidlidinternetaccountname"></a><span data-ttu-id="cf7d5-103">PidLidInternetAccountName</span><span class="sxs-lookup"><span data-stu-id="cf7d5-103">PidLidInternetAccountName</span></span>

<span data-ttu-id="cf7d5-104">返回发送邮件的帐户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-104">Returns the display name of the account that delivered the message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="cf7d5-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="cf7d5-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="cf7d5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cf7d5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cf7d5-107">dispidInetAcctName</span><span class="sxs-lookup"><span data-stu-id="cf7d5-107">dispidInetAcctName</span></span>  <br/> |
|<span data-ttu-id="cf7d5-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cf7d5-108">Property set:</span></span>  <br/> |<span data-ttu-id="cf7d5-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="cf7d5-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="cf7d5-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cf7d5-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cf7d5-111">0x00008580</span><span class="sxs-lookup"><span data-stu-id="cf7d5-111">0x00008580</span></span>  <br/> |
|<span data-ttu-id="cf7d5-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cf7d5-112">Data type:</span></span>  <br/> |<span data-ttu-id="cf7d5-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cf7d5-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="cf7d5-114">区域：</span><span class="sxs-lookup"><span data-stu-id="cf7d5-114">Area:</span></span>  <br/> |<span data-ttu-id="cf7d5-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="cf7d5-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cf7d5-116">说明</span><span class="sxs-lookup"><span data-stu-id="cf7d5-116">Remarks</span></span>

<span data-ttu-id="cf7d5-117">此属性应包含从发送邮件的帐户的帐户管理 API 属性[PROP_ACCT_NAME](prop_acct_name.md)返回的值相同。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-117">This property should contain the same value that is returned from the Account Management API property [PROP_ACCT_NAME](prop_acct_name.md) for the account that delivered the message.</span></span> 
  
<span data-ttu-id="cf7d5-118">消息存储提供程序公开此命名的属性和[PidLidInternetAccountStamp](pidlidinternetaccountstamp.md) ，以便执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf7d5-118">Message store providers expose this named property and [PidLidInternetAccountStamp](pidlidinternetaccountstamp.md) so that the following actions occur:</span></span> 
  
- <span data-ttu-id="cf7d5-119">当用户在电子邮件中单击**全部答复**时，Outlook 将删除与该帐户相关联，并从收件人列表的答复邮件上标记的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-119">When a user clicks **Reply to All** in an email message, Outlook removes the email address that is associated with the account and is stamped on the message from the recipient list of the reply.</span></span> <span data-ttu-id="cf7d5-120">除非此电子邮件地址是原始邮件的发件人，将发生此问题。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-120">This behavior occurs unless this email address is the sender of the original message.</span></span> 
    
- <span data-ttu-id="cf7d5-121">默认情况下，Outlook 发送答复和转发的邮件通过标原始邮件上的帐户。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-121">By default, Outlook sends replies and forwarded messages through the account that is stamped on the original message.</span></span>
    
<span data-ttu-id="cf7d5-122">通常，Outlook 协议经理提供了邮件，和 Outlook 设置**PidLidInternetAccountName**和**PidLidInternetAccountStamp**属性来指示发送邮件的帐户。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-122">Usually, the Outlook Protocol Manager delivers messages, and Outlook sets the **PidLidInternetAccountName** and **PidLidInternetAccountStamp** properties to indicate the account that delivered the message.</span></span> <span data-ttu-id="cf7d5-123">但是，如果与传输紧密耦合的消息存储，Outlook 协议经理不传递邮件和 Outlook 无法设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-123">However, if a message store is tightly coupled with a transport, the Outlook Protocol Manager does not deliver messages and Outlook cannot set these properties.</span></span> <span data-ttu-id="cf7d5-124">在此方案中，Outlook 调用[IMAPIProp::GetIDsFromNames](http://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx)函数。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-124">In this scenario, Outlook calls the [IMAPIProp::GetIDsFromNames](http://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx) function.</span></span> <span data-ttu-id="cf7d5-125">如果希望公开这些命名的属性的消息存储提供程序，它应实现**IMAPIProp::GetIDsFromNames**并返回通过输出参数*lppPropTags*属性标记。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-125">If the message store provider wants to expose these named properties, it should implement **IMAPIProp::GetIDsFromNames** and return property tags through the output parameter  *lppPropTags*  .</span></span> <span data-ttu-id="cf7d5-126">Outlook 可通过使用这些属性标记，然后调用[IMAPIProp::GetProps](http://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx)方法和消息存储提供程序可以返回帐户名和图章的所需的帐户。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-126">Outlook can then call the [IMAPIProp::GetProps](http://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx) method by using these property tags, and the message store provider can return the account name and stamp of the desired account.</span></span> 
  
<span data-ttu-id="cf7d5-127">若要支持这些命名属性，存储提供程序应产生预期 Outlook 使用**IMAPIProp::GetIDsFromNames**来获取此属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-127">To support these named properties, store providers should expect Outlook to use **IMAPIProp::GetIDsFromNames** to obtain the property tag for this property.</span></span> <span data-ttu-id="cf7d5-128">Outlook 指定下列值对应于作为由**IMAPIProp::GetIDsFromNames**输入的参数*lppPropNames*指向在数组的一部分传递此命名属性的[MAPINAMEID](http://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="cf7d5-128">Outlook specifies the following values for the [MAPINAMEID](http://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx) structure that corresponds to this named property, which is passed as part of the array pointed at by the input parameter  *lppPropNames*  of **IMAPIProp::GetIDsFromNames**.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cf7d5-129">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="cf7d5-129">lpGuid:</span></span>  <br/> |<span data-ttu-id="cf7d5-130">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="cf7d5-130">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="cf7d5-131">ulKind:</span><span class="sxs-lookup"><span data-stu-id="cf7d5-131">ulKind:</span></span>  <br/> |<span data-ttu-id="cf7d5-132">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="cf7d5-132">MNID_ID</span></span>  <br/> |
|<span data-ttu-id="cf7d5-133">Kind.lID:</span><span class="sxs-lookup"><span data-stu-id="cf7d5-133">Kind.lID:</span></span>  <br/> |<span data-ttu-id="cf7d5-134">dispidInetAcctName</span><span class="sxs-lookup"><span data-stu-id="cf7d5-134">dispidInetAcctName</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cf7d5-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf7d5-135">See also</span></span>

- [<span data-ttu-id="cf7d5-136">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="cf7d5-136">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="cf7d5-137">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="cf7d5-137">Constants (Account management API)</span></span>](constants-account-management-api.md)
- [<span data-ttu-id="cf7d5-138">PidLidInternetAccountName 规范属性</span><span class="sxs-lookup"><span data-stu-id="cf7d5-138">PidLidInternetAccountName Canonical Property</span></span>](http://msdn.microsoft.com/library/29bedadf-903d-419d-804d-dc8bd92b745d%28Office.15%29.aspx)

