---
title: PidTagNextSendAcct
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1cf5b314-39fa-996f-fd88-00380ffbc4de
description: 指定邮件的辅助 accountsendstamp。
ms.openlocfilehash: 3aa88a1fd5a73cc4ae2e990e6dad0697083bb694
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327711"
---
# <a name="pidtagnextsendacct"></a><span data-ttu-id="7b9f6-103">PidTagNextSendAcct</span><span class="sxs-lookup"><span data-stu-id="7b9f6-103">PidTagNextSendAcct</span></span>

<span data-ttu-id="7b9f6-104">指定邮件的辅助帐户 "发送" 标记。</span><span class="sxs-lookup"><span data-stu-id="7b9f6-104">Specifies the secondary account "send" stamp for the message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7b9f6-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="7b9f6-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7b9f6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7b9f6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7b9f6-107">PR_NEXT_SEND_ACCT</span><span class="sxs-lookup"><span data-stu-id="7b9f6-107">PR_NEXT_SEND_ACCT</span></span>  <br/> |
|<span data-ttu-id="7b9f6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7b9f6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7b9f6-109">0x0E29</span><span class="sxs-lookup"><span data-stu-id="7b9f6-109">0x0E29</span></span>  <br/> |
|<span data-ttu-id="7b9f6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7b9f6-110">Data type:</span></span>  <br/> |<span data-ttu-id="7b9f6-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7b9f6-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7b9f6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7b9f6-112">Area:</span></span>  <br/> |<span data-ttu-id="7b9f6-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="7b9f6-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7b9f6-114">注解</span><span class="sxs-lookup"><span data-stu-id="7b9f6-114">Remarks</span></span>

<span data-ttu-id="7b9f6-115">此属性适用于 MAPI 邮件对象。</span><span class="sxs-lookup"><span data-stu-id="7b9f6-115">This property applies to a MAPI message object.</span></span> <span data-ttu-id="7b9f6-116">对于收到的邮件, 第二个帐户 "发送" 标记指示转发或答复应与之一起发送的帐户 (如果无法使用主帐户发送转发或答复)。</span><span class="sxs-lookup"><span data-stu-id="7b9f6-116">For a received message, the secondary account "send" stamp indicates which account a forward or a reply should be sent with, if the forward or reply cannot be sent with the primary account.</span></span> <span data-ttu-id="7b9f6-117">对于传出邮件, 如果无法使用主帐户发送邮件, 则辅助帐户 "发送" 图章将决定发送邮件的帐户。</span><span class="sxs-lookup"><span data-stu-id="7b9f6-117">For an outgoing message, the secondary account "send" stamp determines with which account to send the message, if the message cannot be sent with the primary account.</span></span> <span data-ttu-id="7b9f6-118">它的值是要向其发送邮件的帐户的[IOlkAccount](iolkaccount.md)接口中的[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md)值。</span><span class="sxs-lookup"><span data-stu-id="7b9f6-118">Its value is the [PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md) value from the [IOlkAccount](iolkaccount.md) interface of the account with which the message is being sent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7b9f6-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b9f6-119">See also</span></span>

- [<span data-ttu-id="7b9f6-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="7b9f6-120">Constants (Account management API)</span></span>](constants-account-management-api.md)
- [<span data-ttu-id="7b9f6-121">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7b9f6-121">MAPI Properties</span></span>](https://msdn.microsoft.com/library/3b980217-b65b-442b-8c18-b8b9f3ff487a%28Office.15%29.aspx) 
- [<span data-ttu-id="7b9f6-122">PidTagNextSendAcct 规范属性</span><span class="sxs-lookup"><span data-stu-id="7b9f6-122">PidTagNextSendAcct Canonical Property</span></span>](https://msdn.microsoft.com/library/b7429c2e-0d9d-4921-9f56-9ecad817f8cb%28Office.15%29.aspx)

