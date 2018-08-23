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
ms.openlocfilehash: 65255e14fd849d730e92bd86027642eef2c687bc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584973"
---
# <a name="hide-meeting-update-option-property"></a><span data-ttu-id="66d61-103">隐藏会议更新选项属性</span><span class="sxs-lookup"><span data-stu-id="66d61-103">Hide Meeting Update Option Property</span></span>

  
  
<span data-ttu-id="66d61-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66d61-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66d61-105">隐藏该选项发送给仅添加或删除的与会者的会议更新。</span><span class="sxs-lookup"><span data-stu-id="66d61-105">Hides the option to send meeting updates to only added or deleted attendees.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="66d61-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="66d61-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="66d61-107">公开上：</span><span class="sxs-lookup"><span data-stu-id="66d61-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="66d61-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="66d61-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="66d61-109">通过创建：</span><span class="sxs-lookup"><span data-stu-id="66d61-109">Created by:</span></span>  <br/> |<span data-ttu-id="66d61-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="66d61-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="66d61-111">通过来访问：</span><span class="sxs-lookup"><span data-stu-id="66d61-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="66d61-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="66d61-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="66d61-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="66d61-113">Property type:</span></span>  <br/> |<span data-ttu-id="66d61-114">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="66d61-114">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="66d61-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="66d61-115">Access type:</span></span>  <br/> |<span data-ttu-id="66d61-116">读/写</span><span class="sxs-lookup"><span data-stu-id="66d61-116">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="66d61-117">备注</span><span class="sxs-lookup"><span data-stu-id="66d61-117">Remarks</span></span>

<span data-ttu-id="66d61-118">若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="66d61-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="66d61-119">当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="66d61-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="66d61-120">[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="66d61-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="66d61-121">若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。</span><span class="sxs-lookup"><span data-stu-id="66d61-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="66d61-122">调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：</span><span class="sxs-lookup"><span data-stu-id="66d61-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="66d61-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="66d61-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="66d61-124">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="66d61-124">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="66d61-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="66d61-125">ulKind:</span></span>  <br/> |<span data-ttu-id="66d61-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="66d61-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="66d61-127">Kind.lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="66d61-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="66d61-128">L"urn： 架构-microsoft-com:office:outlook #allornonemtgupdatedlg"</span><span class="sxs-lookup"><span data-stu-id="66d61-128">L"urn:schemas-microsoft-com:office:outlook#allornonemtgupdatedlg"</span></span>  <br/> |
   
<span data-ttu-id="66d61-129">使用服务器发送会议更新存储提供程序可以修改**向与会者发送更新**对话框。</span><span class="sxs-lookup"><span data-stu-id="66d61-129">A store provider that uses a server to send meeting updates can modify the **Send Update to Attendees** dialog box.</span></span> <span data-ttu-id="66d61-130">此功能很有用，因为当服务器发送会议更新时，服务器不知道哪些与会者已添加或删除以来初始会议请求的用户。</span><span class="sxs-lookup"><span data-stu-id="66d61-130">This functionality is useful because when the server sends a meeting update, the server does not know which attendees have been added or deleted by the user since the initial meeting request.</span></span> <span data-ttu-id="66d61-131">当此属性为**true**时，**发送给添加或删除的与会者仅更新**选项不会显示在**向与会者发送更新**对话框。</span><span class="sxs-lookup"><span data-stu-id="66d61-131">When this property is **true**, the **Send update only to added or deleted attendees** option is not displayed in the **Send Update to Attendees** dialog box.</span></span> 
  
<span data-ttu-id="66d61-132">如果 Outlook 版本早于 Microsoft Office Outlook 2003 Service Pack 1，或如果其值为**false**，则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="66d61-132">This property is ignored if the version of Outlook is earlier than Microsoft Office Outlook 2003 Service Pack 1, or if its value is **false**.</span></span>
  

