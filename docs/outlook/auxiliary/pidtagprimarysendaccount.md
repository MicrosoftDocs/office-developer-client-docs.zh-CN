---
title: PidTagPrimarySendAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e1bc4900-d261-f692-386b-139ef6960212
description: 指定邮件的主 accountsendstamp。
ms.openlocfilehash: 902c71bd4a1bd5a25ab50c4b26bcfa6d5e8489e6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327704"
---
# <a name="pidtagprimarysendaccount"></a><span data-ttu-id="243bf-103">PidTagPrimarySendAccount</span><span class="sxs-lookup"><span data-stu-id="243bf-103">PidTagPrimarySendAccount</span></span>

<span data-ttu-id="243bf-104">指定邮件的主帐户 "发送" 标记。</span><span class="sxs-lookup"><span data-stu-id="243bf-104">Specifies the primary account "send" stamp for a message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="243bf-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="243bf-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="243bf-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="243bf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="243bf-107">PR_PRIMARY_SEND_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="243bf-107">PR_PRIMARY_SEND_ACCOUNT</span></span>  <br/> |
|<span data-ttu-id="243bf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="243bf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="243bf-109">0x0E28</span><span class="sxs-lookup"><span data-stu-id="243bf-109">0x0E28</span></span>  <br/> |
|<span data-ttu-id="243bf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="243bf-110">Data type:</span></span>  <br/> |<span data-ttu-id="243bf-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="243bf-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="243bf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="243bf-112">Area:</span></span>  <br/> |<span data-ttu-id="243bf-113">帐户</span><span class="sxs-lookup"><span data-stu-id="243bf-113">Account</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="243bf-114">注解</span><span class="sxs-lookup"><span data-stu-id="243bf-114">Remarks</span></span>

<span data-ttu-id="243bf-115">此属性适用于 MAPI 邮件对象。</span><span class="sxs-lookup"><span data-stu-id="243bf-115">This property applies to a MAPI message object.</span></span> <span data-ttu-id="243bf-116">对于已接收的邮件, 主帐户 "发送" 标记指示转发或答复应与之一起发送的帐户。</span><span class="sxs-lookup"><span data-stu-id="243bf-116">For a received message, the primary account "send" stamp indicates which account a forward or a reply should be sent with.</span></span> <span data-ttu-id="243bf-117">对于传出邮件, 它确定要向哪个帐户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="243bf-117">For an outgoing message, it determines which account to send the message with.</span></span> <span data-ttu-id="243bf-118">它的值是要向其发送邮件的帐户的[IOlkAccount](iolkaccount.md)接口中的[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md)值。</span><span class="sxs-lookup"><span data-stu-id="243bf-118">Its value is the [PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md) value from the [IOlkAccount](iolkaccount.md) interface of the account with which the message is being sent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="243bf-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="243bf-119">See also</span></span>

- [<span data-ttu-id="243bf-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="243bf-120">Constants (Account management API)</span></span>](constants-account-management-api.md)
- [<span data-ttu-id="243bf-121">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="243bf-121">MAPI Properties</span></span>](https://msdn.microsoft.com/library/3b980217-b65b-442b-8c18-b8b9f3ff487a%28Office.15%29.aspx)
- [<span data-ttu-id="243bf-122">PidTagPrimarySendAccount 规范属性</span><span class="sxs-lookup"><span data-stu-id="243bf-122">PidTagPrimarySendAccount Canonical Property</span></span>](https://msdn.microsoft.com/library/2f268b3b-2e4c-4aea-8879-bdd0ac1df35c%28Office.15%29.aspx)

