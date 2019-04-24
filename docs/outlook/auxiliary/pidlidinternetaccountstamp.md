---
title: PidLidInternetAccountStamp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 52003a4e-1b61-2965-5204-6601652dd15b
description: 返回传递邮件的帐户的帐户戳。
ms.openlocfilehash: c5da45268cefbe09588fdcfcda32e4e7a4be9d5f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327725"
---
# <a name="pidlidinternetaccountstamp"></a><span data-ttu-id="3a703-103">PidLidInternetAccountStamp</span><span class="sxs-lookup"><span data-stu-id="3a703-103">PidLidInternetAccountStamp</span></span>

<span data-ttu-id="3a703-104">返回传递邮件的帐户的帐户戳。</span><span class="sxs-lookup"><span data-stu-id="3a703-104">Returns the account stamp of the account that delivered the message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="3a703-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="3a703-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3a703-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3a703-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3a703-107">dispidInetAcctStamp</span><span class="sxs-lookup"><span data-stu-id="3a703-107">dispidInetAcctStamp</span></span>  <br/> |
|<span data-ttu-id="3a703-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="3a703-108">Property set:</span></span>  <br/> |<span data-ttu-id="3a703-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="3a703-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="3a703-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="3a703-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="3a703-111">0x00008581</span><span class="sxs-lookup"><span data-stu-id="3a703-111">0x00008581</span></span>  <br/> |
|<span data-ttu-id="3a703-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3a703-112">Data type:</span></span>  <br/> |<span data-ttu-id="3a703-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3a703-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3a703-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3a703-114">Area:</span></span>  <br/> |<span data-ttu-id="3a703-115">常规邮件</span><span class="sxs-lookup"><span data-stu-id="3a703-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3a703-116">注解</span><span class="sxs-lookup"><span data-stu-id="3a703-116">Remarks</span></span>

<span data-ttu-id="3a703-117">此属性应包含的值与传递邮件的帐户的帐户管理 API 属性[PROP_ACCT_STAMP](prop_acct_stamp.md)返回的值相同。</span><span class="sxs-lookup"><span data-stu-id="3a703-117">This property should contain the same value that is returned from the Account Management API property [PROP_ACCT_STAMP](prop_acct_stamp.md) for the account that delivered the message.</span></span> 
  
<span data-ttu-id="3a703-118">邮件存储提供程序公开此命名属性和[PidLidInternetAccountName](pidlidinternetaccountname.md) , 以便执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3a703-118">Message store providers expose this named property and [PidLidInternetAccountName](pidlidinternetaccountname.md) so that the following actions occur:</span></span> 
  
- <span data-ttu-id="3a703-119">当用户单击电子邮件中的 "**全部答复**" 时, Outlook 将删除与该帐户关联的电子邮件地址, 并将其标记为答复邮件的收件人列表中的邮件。</span><span class="sxs-lookup"><span data-stu-id="3a703-119">When a user clicks **Reply to All** in an email message, Outlook removes the email address that is associated with the account and is stamped on the message from the recipient list of the reply.</span></span> <span data-ttu-id="3a703-120">如果此电子邮件地址是原始邮件的发件人, 则会出现此行为。</span><span class="sxs-lookup"><span data-stu-id="3a703-120">This behavior occurs unless this email address is the sender of the original message.</span></span> 
    
- <span data-ttu-id="3a703-121">默认情况下, Outlook 通过原始邮件上标记的帐户发送答复邮件和转发邮件。</span><span class="sxs-lookup"><span data-stu-id="3a703-121">By default, Outlook sends replies and forwarded messages through the account that is stamped on the original message.</span></span>
    
<span data-ttu-id="3a703-122">通常情况下, outlook 协议管理器会传递邮件, outlook 会设置**PidLidInternetAccountName**和**PidLidInternetAccountStamp**属性, 以指示传递邮件的帐户。</span><span class="sxs-lookup"><span data-stu-id="3a703-122">Usually, the Outlook Protocol Manager delivers messages, and Outlook sets the **PidLidInternetAccountName** and **PidLidInternetAccountStamp** properties to indicate the account that delivered the message.</span></span> <span data-ttu-id="3a703-123">但是, 如果邮件存储与传输紧密结合, outlook 协议管理器将不传递邮件, 并且 outlook 无法设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="3a703-123">However, if a message store is tightly coupled with a transport, the Outlook Protocol Manager does not deliver messages and Outlook cannot set these properties.</span></span> <span data-ttu-id="3a703-124">在这种情况下, Outlook 将调用[IMAPIProp:: GetIDsFromNames](https://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx)函数。</span><span class="sxs-lookup"><span data-stu-id="3a703-124">In this scenario, Outlook calls the [IMAPIProp::GetIDsFromNames](https://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx) function.</span></span> <span data-ttu-id="3a703-125">如果邮件存储区提供程序想要公开这些命名属性, 它应通过 output parameter *lppPropTags*实现**IMAPIProp:: GetIDsFromNames**和返回属性标记。</span><span class="sxs-lookup"><span data-stu-id="3a703-125">If the message store provider wants to expose these named properties, it should implement **IMAPIProp::GetIDsFromNames** and return property tags through the output parameter  *lppPropTags*  .</span></span> <span data-ttu-id="3a703-126">然后, Outlook 可以使用这些属性标记调用[IMAPIProp:: GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx)方法, 邮件存储区提供程序可以返回所需帐户的帐户名称和 stamp。</span><span class="sxs-lookup"><span data-stu-id="3a703-126">Outlook can then call the [IMAPIProp::GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx) method by using these property tags, and the message store provider can return the account name and stamp of the desired account.</span></span> 
  
<span data-ttu-id="3a703-127">若要支持这些命名属性, 存储提供程序应期望 Outlook 使用**IMAPIProp:: GetIDsFromNames**获取此属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="3a703-127">To support these named properties, store providers should expect Outlook to use **IMAPIProp::GetIDsFromNames** to obtain the property tag for this property.</span></span> <span data-ttu-id="3a703-128">Outlook 指定与此命名属性对应的[MAPINAMEID](https://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx)结构的以下值, 该属性作为由**IMAPIProp:: GetIDsFromNames**的输入参数*lppPropNames*所指向的数组的一部分进行传递。</span><span class="sxs-lookup"><span data-stu-id="3a703-128">Outlook specifies the following values for the [MAPINAMEID](https://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx) structure that corresponds to this named property, which is passed as part of the array pointed at by the input parameter  *lppPropNames*  of **IMAPIProp::GetIDsFromNames**.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3a703-129">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="3a703-129">lpGuid:</span></span>  <br/> |<span data-ttu-id="3a703-130">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="3a703-130">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="3a703-131">ulKind:</span><span class="sxs-lookup"><span data-stu-id="3a703-131">ulKind:</span></span>  <br/> |<span data-ttu-id="3a703-132">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="3a703-132">MNID_ID</span></span>  <br/> |
|<span data-ttu-id="3a703-133">类型盖子:</span><span class="sxs-lookup"><span data-stu-id="3a703-133">Kind.lID:</span></span>  <br/> |<span data-ttu-id="3a703-134">dispidInetAcctStamp</span><span class="sxs-lookup"><span data-stu-id="3a703-134">dispidInetAcctStamp</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3a703-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a703-135">See also</span></span>

- [<span data-ttu-id="3a703-136">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="3a703-136">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="3a703-137">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="3a703-137">Constants (Account management API)</span></span>](constants-account-management-api.md)
- [<span data-ttu-id="3a703-138">PidLidInternetAccountStamp 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a703-138">PidLidInternetAccountStamp Canonical Property</span></span>](https://msdn.microsoft.com/library/819179fe-e58e-415c-abc7-1949036745ee%28Office.15%29.aspx)

