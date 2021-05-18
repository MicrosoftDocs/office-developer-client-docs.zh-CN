---
title: PidLidInternetAccountName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 5acca047-ff2a-716c-8dd4-b676fce1a3cf
description: 返回显示名称邮件的帐户的收件人。
ms.openlocfilehash: 2bd27cc7f868fb3f255a002ed70d0cb9b79516e3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327683"
---
# <a name="pidlidinternetaccountname"></a><span data-ttu-id="4190c-103">PidLidInternetAccountName</span><span class="sxs-lookup"><span data-stu-id="4190c-103">PidLidInternetAccountName</span></span>

<span data-ttu-id="4190c-104">返回显示名称邮件的帐户的收件人。</span><span class="sxs-lookup"><span data-stu-id="4190c-104">Returns the display name of the account that delivered the message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="4190c-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="4190c-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4190c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4190c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4190c-107">dispidInetAcctName</span><span class="sxs-lookup"><span data-stu-id="4190c-107">dispidInetAcctName</span></span>  <br/> |
|<span data-ttu-id="4190c-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="4190c-108">Property set:</span></span>  <br/> |<span data-ttu-id="4190c-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="4190c-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="4190c-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="4190c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="4190c-111">0x00008580</span><span class="sxs-lookup"><span data-stu-id="4190c-111">0x00008580</span></span>  <br/> |
|<span data-ttu-id="4190c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4190c-112">Data type:</span></span>  <br/> |<span data-ttu-id="4190c-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4190c-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="4190c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="4190c-114">Area:</span></span>  <br/> |<span data-ttu-id="4190c-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="4190c-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4190c-116">备注</span><span class="sxs-lookup"><span data-stu-id="4190c-116">Remarks</span></span>

<span data-ttu-id="4190c-117">此属性应包含从传递邮件的帐户的 Account Management API [PROP_ACCT_NAME](prop_acct_name.md) 返回的相同值。</span><span class="sxs-lookup"><span data-stu-id="4190c-117">This property should contain the same value that is returned from the Account Management API property [PROP_ACCT_NAME](prop_acct_name.md) for the account that delivered the message.</span></span> 
  
<span data-ttu-id="4190c-118">邮件存储提供程序公开此命名属性和 [PidLidInternetAccountStamp，](pidlidinternetaccountstamp.md) 以便发生以下操作：</span><span class="sxs-lookup"><span data-stu-id="4190c-118">Message store providers expose this named property and [PidLidInternetAccountStamp](pidlidinternetaccountstamp.md) so that the following actions occur:</span></span> 
  
- <span data-ttu-id="4190c-119">当用户 **在电子邮件中** 单击"全部答复"时，Outlook 将删除与帐户关联的电子邮件地址，并从回复的收件人列表中在邮件上标记该地址。</span><span class="sxs-lookup"><span data-stu-id="4190c-119">When a user clicks **Reply to All** in an email message, Outlook removes the email address that is associated with the account and is stamped on the message from the recipient list of the reply.</span></span> <span data-ttu-id="4190c-120">除非此电子邮件地址是原始邮件的发件人，否则会发生此行为。</span><span class="sxs-lookup"><span data-stu-id="4190c-120">This behavior occurs unless this email address is the sender of the original message.</span></span> 
    
- <span data-ttu-id="4190c-121">默认情况下，Outlook 通过原始邮件上标记的帐户发送答复和转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="4190c-121">By default, Outlook sends replies and forwarded messages through the account that is stamped on the original message.</span></span>
    
<span data-ttu-id="4190c-122">通常，Outlook 协议管理器传递邮件，Outlook 设置 **PidLidInternetAccountName** 和 **PidLidInternetAccountStamp** 属性以指示传递邮件的帐户。</span><span class="sxs-lookup"><span data-stu-id="4190c-122">Usually, the Outlook Protocol Manager delivers messages, and Outlook sets the **PidLidInternetAccountName** and **PidLidInternetAccountStamp** properties to indicate the account that delivered the message.</span></span> <span data-ttu-id="4190c-123">但是，如果邮件存储与传输紧密结合，则 Outlook 协议管理器不会传递邮件，并且 Outlook 无法设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="4190c-123">However, if a message store is tightly coupled with a transport, the Outlook Protocol Manager does not deliver messages and Outlook cannot set these properties.</span></span> <span data-ttu-id="4190c-124">在此方案中，Outlook 调用 [IMAPIProp：：GetIDsFromNames](https://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx) 函数。</span><span class="sxs-lookup"><span data-stu-id="4190c-124">In this scenario, Outlook calls the [IMAPIProp::GetIDsFromNames](https://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx) function.</span></span> <span data-ttu-id="4190c-125">如果邮件存储提供程序想要公开这些命名属性，它应实现 **IMAPIProp：：GetIDsFromNames** 并通过输出参数  *lppPropTags*  返回属性标记。</span><span class="sxs-lookup"><span data-stu-id="4190c-125">If the message store provider wants to expose these named properties, it should implement **IMAPIProp::GetIDsFromNames** and return property tags through the output parameter  *lppPropTags*  .</span></span> <span data-ttu-id="4190c-126">然后，Outlook 可以使用这些属性标记调用 [IMAPIProp：：GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx) 方法，并且邮件存储提供程序可以返回所需帐户的帐户名称和标记。</span><span class="sxs-lookup"><span data-stu-id="4190c-126">Outlook can then call the [IMAPIProp::GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx) method by using these property tags, and the message store provider can return the account name and stamp of the desired account.</span></span> 
  
<span data-ttu-id="4190c-127">为了支持这些命名属性，存储提供程序应该希望 Outlook 使用 **IMAPIProp：：GetIDsFromNames** 获取此属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="4190c-127">To support these named properties, store providers should expect Outlook to use **IMAPIProp::GetIDsFromNames** to obtain the property tag for this property.</span></span> <span data-ttu-id="4190c-128">Outlook 为对应于此命名属性的 [MAPINAMEID](https://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx)结构指定以下值，该属性作为 **IMAPIProp：：GetIDsFromNames** 的输入参数 *lppPropNames* 指向的数组的一部分传递。</span><span class="sxs-lookup"><span data-stu-id="4190c-128">Outlook specifies the following values for the [MAPINAMEID](https://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx) structure that corresponds to this named property, which is passed as part of the array pointed at by the input parameter  *lppPropNames*  of **IMAPIProp::GetIDsFromNames**.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4190c-129">lpGuid：</span><span class="sxs-lookup"><span data-stu-id="4190c-129">lpGuid:</span></span>  <br/> |<span data-ttu-id="4190c-130">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="4190c-130">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="4190c-131">ulKind：</span><span class="sxs-lookup"><span data-stu-id="4190c-131">ulKind:</span></span>  <br/> |<span data-ttu-id="4190c-132">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="4190c-132">MNID_ID</span></span>  <br/> |
|<span data-ttu-id="4190c-133">Kind.lID：</span><span class="sxs-lookup"><span data-stu-id="4190c-133">Kind.lID:</span></span>  <br/> |<span data-ttu-id="4190c-134">dispidInetAcctName</span><span class="sxs-lookup"><span data-stu-id="4190c-134">dispidInetAcctName</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4190c-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4190c-135">See also</span></span>

- [<span data-ttu-id="4190c-136">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="4190c-136">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="4190c-137">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="4190c-137">Constants (Account management API)</span></span>](constants-account-management-api.md)
- [<span data-ttu-id="4190c-138">PidLidInternetAccountName 规范属性</span><span class="sxs-lookup"><span data-stu-id="4190c-138">PidLidInternetAccountName Canonical Property</span></span>](https://msdn.microsoft.com/library/29bedadf-903d-419d-804d-dc8bd92b745d%28Office.15%29.aspx)

