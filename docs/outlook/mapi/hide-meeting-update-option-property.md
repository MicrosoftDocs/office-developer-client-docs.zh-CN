---
title: 隐藏会议更新选项属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- Hide Meeting Update Option Property
api_type:
- COM
ms.assetid: 9e7b413f-a88a-a4ec-8d57-1f3058cce4a4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ac7c891fa05560231a257f9bd52ccbbfe564b49d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299508"
---
# <a name="hide-meeting-update-option-property"></a><span data-ttu-id="471ae-103">隐藏会议更新选项属性</span><span class="sxs-lookup"><span data-stu-id="471ae-103">Hide Meeting Update Option Property</span></span>

  
  
<span data-ttu-id="471ae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="471ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="471ae-105">隐藏将会议更新仅发送给已添加或已删除的与会者的选项。</span><span class="sxs-lookup"><span data-stu-id="471ae-105">Hides the option to send meeting updates to only added or deleted attendees.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="471ae-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="471ae-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="471ae-107">公开于:</span><span class="sxs-lookup"><span data-stu-id="471ae-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="471ae-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="471ae-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="471ae-109">创建者:</span><span class="sxs-lookup"><span data-stu-id="471ae-109">Created by:</span></span>  <br/> |<span data-ttu-id="471ae-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="471ae-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="471ae-111">访问者:</span><span class="sxs-lookup"><span data-stu-id="471ae-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="471ae-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="471ae-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="471ae-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="471ae-113">Property type:</span></span>  <br/> |<span data-ttu-id="471ae-114">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="471ae-114">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="471ae-115">访问类型:</span><span class="sxs-lookup"><span data-stu-id="471ae-115">Access type:</span></span>  <br/> |<span data-ttu-id="471ae-116">读/写</span><span class="sxs-lookup"><span data-stu-id="471ae-116">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="471ae-117">注解</span><span class="sxs-lookup"><span data-stu-id="471ae-117">Remarks</span></span>

<span data-ttu-id="471ae-118">若要提供任何存储功能, 存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md) , 并返回传递给[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)调用的任何这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="471ae-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="471ae-119">当这些属性中任一属性的属性标记传递给[IMAPIProp:: GetProps](imapiprop-getprops.md)时, 存储提供程序还必须返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="471ae-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="471ae-120">存储提供程序可以调用[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)以获取或设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="471ae-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="471ae-121">若要检索此属性的值, 客户端应首先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。</span><span class="sxs-lookup"><span data-stu-id="471ae-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="471ae-122">调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定以下值:</span><span class="sxs-lookup"><span data-stu-id="471ae-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="471ae-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="471ae-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="471ae-124">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="471ae-124">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="471ae-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="471ae-125">ulKind:</span></span>  <br/> |<span data-ttu-id="471ae-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="471ae-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="471ae-127">类型 lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="471ae-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="471ae-128">L "urn: 架构-microsoft-com: office: outlook # allornonemtgupdatedlg"</span><span class="sxs-lookup"><span data-stu-id="471ae-128">L"urn:schemas-microsoft-com:office:outlook#allornonemtgupdatedlg"</span></span>  <br/> |
   
<span data-ttu-id="471ae-129">使用服务器发送会议更新的存储提供程序可以修改 "**将更新发送到与会者**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="471ae-129">A store provider that uses a server to send meeting updates can modify the **Send Update to Attendees** dialog box.</span></span> <span data-ttu-id="471ae-130">此功能很有用, 因为当服务器发送会议更新时, 服务器不知道自最初会议请求以来用户添加或删除了哪些与会者。</span><span class="sxs-lookup"><span data-stu-id="471ae-130">This functionality is useful because when the server sends a meeting update, the server does not know which attendees have been added or deleted by the user since the initial meeting request.</span></span> <span data-ttu-id="471ae-131">当此属性为**true**时, "发送**或删除的与会者发送或删除的与会者**" 选项不会显示在 "**发送到与会者的更新**" 对话框中。</span><span class="sxs-lookup"><span data-stu-id="471ae-131">When this property is **true**, the **Send update only to added or deleted attendees** option is not displayed in the **Send Update to Attendees** dialog box.</span></span> 
  
<span data-ttu-id="471ae-132">如果 Outlook 的版本早于 Microsoft Office Outlook 2003 Service Pack 1, 或者其值为**false**, 则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="471ae-132">This property is ignored if the version of Outlook is earlier than Microsoft Office Outlook 2003 Service Pack 1, or if its value is **false**.</span></span>
  

