---
title: PidTagPrimarySendAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e1bc4900-d261-f692-386b-139ef6960212
description: 指定邮件主 accountsendstamp。
ms.openlocfilehash: 902c71bd4a1bd5a25ab50c4b26bcfa6d5e8489e6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394081"
---
# <a name="pidtagprimarysendaccount"></a><span data-ttu-id="d9cb0-103">PidTagPrimarySendAccount</span><span class="sxs-lookup"><span data-stu-id="d9cb0-103">PidTagPrimarySendAccount</span></span>

<span data-ttu-id="d9cb0-104">指定一条消息的主帐户"发送"戳。</span><span class="sxs-lookup"><span data-stu-id="d9cb0-104">Specifies the primary account "send" stamp for a message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d9cb0-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d9cb0-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d9cb0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d9cb0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d9cb0-107">PR_PRIMARY_SEND_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="d9cb0-107">PR_PRIMARY_SEND_ACCOUNT</span></span>  <br/> |
|<span data-ttu-id="d9cb0-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d9cb0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d9cb0-109">0x0E28</span><span class="sxs-lookup"><span data-stu-id="d9cb0-109">0x0E28</span></span>  <br/> |
|<span data-ttu-id="d9cb0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d9cb0-110">Data type:</span></span>  <br/> |<span data-ttu-id="d9cb0-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d9cb0-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d9cb0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d9cb0-112">Area:</span></span>  <br/> |<span data-ttu-id="d9cb0-113">Account</span><span class="sxs-lookup"><span data-stu-id="d9cb0-113">Account</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d9cb0-114">说明</span><span class="sxs-lookup"><span data-stu-id="d9cb0-114">Remarks</span></span>

<span data-ttu-id="d9cb0-115">此属性适用于 MAPI message 对象。</span><span class="sxs-lookup"><span data-stu-id="d9cb0-115">This property applies to a MAPI message object.</span></span> <span data-ttu-id="d9cb0-116">收到的邮件，主帐户"发送"戳指示转发或答复应发送使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="d9cb0-116">For a received message, the primary account "send" stamp indicates which account a forward or a reply should be sent with.</span></span> <span data-ttu-id="d9cb0-117">对于传出消息，它确定要发送邮件的帐户。</span><span class="sxs-lookup"><span data-stu-id="d9cb0-117">For an outgoing message, it determines which account to send the message with.</span></span> <span data-ttu-id="d9cb0-118">其值是帐户的用于发送邮件的[IOlkAccount](iolkaccount.md)接口的[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md)值。</span><span class="sxs-lookup"><span data-stu-id="d9cb0-118">Its value is the [PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md) value from the [IOlkAccount](iolkaccount.md) interface of the account with which the message is being sent.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d9cb0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9cb0-119">See also</span></span>

- [<span data-ttu-id="d9cb0-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="d9cb0-120">Constants (Account management API)</span></span>](constants-account-management-api.md)
- [<span data-ttu-id="d9cb0-121">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d9cb0-121">MAPI Properties</span></span>](https://msdn.microsoft.com/library/3b980217-b65b-442b-8c18-b8b9f3ff487a%28Office.15%29.aspx)
- [<span data-ttu-id="d9cb0-122">PidTagPrimarySendAccount 规范属性</span><span class="sxs-lookup"><span data-stu-id="d9cb0-122">PidTagPrimarySendAccount Canonical Property</span></span>](https://msdn.microsoft.com/library/2f268b3b-2e4c-4aea-8879-bdd0ac1df35c%28Office.15%29.aspx)

