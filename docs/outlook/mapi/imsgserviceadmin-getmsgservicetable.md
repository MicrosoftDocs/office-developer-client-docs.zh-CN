---
title: IMsgServiceAdminGetMsgServiceTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.GetMsgServiceTable
api_type:
- COM
ms.assetid: 064dd5ca-0108-4045-b17b-0bb29cb93346
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5d8e91490cc39c3f259d35a923bb3bcbb2bf6011
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568166"
---
# <a name="imsgserviceadmingetmsgservicetable"></a><span data-ttu-id="bc326-103">IMsgServiceAdmin::GetMsgServiceTable</span><span class="sxs-lookup"><span data-stu-id="bc326-103">IMsgServiceAdmin::GetMsgServiceTable</span></span>

  
  
<span data-ttu-id="bc326-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc326-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc326-105">提供对邮件服务表，该配置文件中的消息服务的列表的访问。</span><span class="sxs-lookup"><span data-stu-id="bc326-105">Provides access to the message service table, a list of the message services in the profile.</span></span>
  
```cpp
HRESULT GetMsgServiceTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="bc326-106">参数</span><span class="sxs-lookup"><span data-stu-id="bc326-106">Parameters</span></span>

 <span data-ttu-id="bc326-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bc326-107">_ulFlags_</span></span>
  
> <span data-ttu-id="bc326-108">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bc326-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="bc326-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="bc326-109">_lppTable_</span></span>
  
> <span data-ttu-id="bc326-110">[输出]指向邮件服务表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="bc326-110">[out] A pointer to a pointer to the message service table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bc326-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bc326-111">Return value</span></span>

<span data-ttu-id="bc326-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc326-112">S_OK</span></span> 
  
> <span data-ttu-id="bc326-113">已成功返回邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="bc326-113">The message service table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bc326-114">注解</span><span class="sxs-lookup"><span data-stu-id="bc326-114">Remarks</span></span>

<span data-ttu-id="bc326-115">**IMsgServiceAdmin::GetMsgServiceTable**方法提供对邮件服务表，一个表，MAPI 维护列出当前在会话配置中安装的消息服务的访问。</span><span class="sxs-lookup"><span data-stu-id="bc326-115">The **IMsgServiceAdmin::GetMsgServiceTable** method provides access to the message service table, a table that MAPI maintains that lists the message services currently installed in the session profile.</span></span> <span data-ttu-id="bc326-116">邮件服务表中的列的完整列表，请参阅[邮件服务表](message-service-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="bc326-116">For a complete list of columns in the message service table, see [Message Service Table](message-service-tables.md).</span></span>
  
<span data-ttu-id="bc326-117">邮件服务表是静态的。</span><span class="sxs-lookup"><span data-stu-id="bc326-117">The message service table is static.</span></span> <span data-ttu-id="bc326-118">客户端具有已向其授予访问后，后续消息服务添加或删除操作不会影响它。</span><span class="sxs-lookup"><span data-stu-id="bc326-118">After a client has been given access to it, subsequent message service additions or deletions will not affect it.</span></span> <span data-ttu-id="bc326-119">如果当前配置文件中没有邮件服务， **GetMsgServiceTable**返回具有零个行的表。</span><span class="sxs-lookup"><span data-stu-id="bc326-119">If there are no message services in the current profile, **GetMsgServiceTable** returns a table with zero rows.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="bc326-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="bc326-120">MFCMAPI reference</span></span>

<span data-ttu-id="bc326-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bc326-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="bc326-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="bc326-122">**File**</span></span>|<span data-ttu-id="bc326-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="bc326-123">**Function**</span></span>|<span data-ttu-id="bc326-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="bc326-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bc326-125">MsgServiceTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="bc326-125">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="bc326-126">CMsgServiceTableDlg::OnRefreshView</span><span class="sxs-lookup"><span data-stu-id="bc326-126">CMsgServiceTableDlg::OnRefreshView</span></span>  <br/> |<span data-ttu-id="bc326-127">MFCMAPI 使用**IMsgServiceAdmin::GetMsgServiceTable**方法加载配置文件以呈现在视图中的服务的表。</span><span class="sxs-lookup"><span data-stu-id="bc326-127">MFCMAPI uses the **IMsgServiceAdmin::GetMsgServiceTable** method to load the table of services in a profile to render in the view.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bc326-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc326-128">See also</span></span>



[<span data-ttu-id="bc326-129">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="bc326-129">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="bc326-130">IMsgServiceAdmin::DeleteMsgService</span><span class="sxs-lookup"><span data-stu-id="bc326-130">IMsgServiceAdmin::DeleteMsgService</span></span>](imsgserviceadmin-deletemsgservice.md)
  
[<span data-ttu-id="bc326-131">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bc326-131">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="bc326-132">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="bc326-132">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

