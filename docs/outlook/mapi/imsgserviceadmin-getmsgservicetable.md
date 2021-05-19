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
ms.openlocfilehash: fcaebb96d4dca4e6bfbee7491dabeafcbd93a2eb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410474"
---
# <a name="imsgserviceadmingetmsgservicetable"></a><span data-ttu-id="c846c-103">IMsgServiceAdmin::GetMsgServiceTable</span><span class="sxs-lookup"><span data-stu-id="c846c-103">IMsgServiceAdmin::GetMsgServiceTable</span></span>

  
  
<span data-ttu-id="c846c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c846c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c846c-105">提供对邮件服务表（配置文件中邮件服务的列表）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c846c-105">Provides access to the message service table, a list of the message services in the profile.</span></span>
  
```cpp
HRESULT GetMsgServiceTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="c846c-106">参数</span><span class="sxs-lookup"><span data-stu-id="c846c-106">Parameters</span></span>

 <span data-ttu-id="c846c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c846c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="c846c-108">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c846c-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="c846c-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="c846c-109">_lppTable_</span></span>
  
> <span data-ttu-id="c846c-110">[out]指向指向邮件服务表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c846c-110">[out] A pointer to a pointer to the message service table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c846c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c846c-111">Return value</span></span>

<span data-ttu-id="c846c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c846c-112">S_OK</span></span> 
  
> <span data-ttu-id="c846c-113">已成功返回邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="c846c-113">The message service table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c846c-114">备注</span><span class="sxs-lookup"><span data-stu-id="c846c-114">Remarks</span></span>

<span data-ttu-id="c846c-115">**IMsgServiceAdmin：：GetMsgServiceTable** 方法提供对邮件服务表的访问，该表是 MAPI 维护的一个表，其中列出了会话配置文件中当前安装的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="c846c-115">The **IMsgServiceAdmin::GetMsgServiceTable** method provides access to the message service table, a table that MAPI maintains that lists the message services currently installed in the session profile.</span></span> <span data-ttu-id="c846c-116">有关邮件服务表中列的完整列表，请参阅 [Message Service Table](message-service-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="c846c-116">For a complete list of columns in the message service table, see [Message Service Table](message-service-tables.md).</span></span>
  
<span data-ttu-id="c846c-117">邮件服务表是静态的。</span><span class="sxs-lookup"><span data-stu-id="c846c-117">The message service table is static.</span></span> <span data-ttu-id="c846c-118">在客户端获得访问权后，后续邮件服务添加或删除操作将不会影响客户端。</span><span class="sxs-lookup"><span data-stu-id="c846c-118">After a client has been given access to it, subsequent message service additions or deletions will not affect it.</span></span> <span data-ttu-id="c846c-119">如果当前配置文件中没有任何邮件服务 **，GetMsgServiceTable** 将返回一个包含零行的表。</span><span class="sxs-lookup"><span data-stu-id="c846c-119">If there are no message services in the current profile, **GetMsgServiceTable** returns a table with zero rows.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c846c-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c846c-120">MFCMAPI reference</span></span>

<span data-ttu-id="c846c-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c846c-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c846c-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="c846c-122">**File**</span></span>|<span data-ttu-id="c846c-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="c846c-123">**Function**</span></span>|<span data-ttu-id="c846c-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="c846c-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c846c-125">MsgServiceTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="c846c-125">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="c846c-126">CMsgServiceTableDlg：：OnRefreshView</span><span class="sxs-lookup"><span data-stu-id="c846c-126">CMsgServiceTableDlg::OnRefreshView</span></span>  <br/> |<span data-ttu-id="c846c-127">MFCMAPI 使用 **IMsgServiceAdmin：：GetMsgServiceTable** 方法在配置文件中加载要呈现在视图中的服务表。</span><span class="sxs-lookup"><span data-stu-id="c846c-127">MFCMAPI uses the **IMsgServiceAdmin::GetMsgServiceTable** method to load the table of services in a profile to render in the view.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c846c-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c846c-128">See also</span></span>



[<span data-ttu-id="c846c-129">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="c846c-129">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="c846c-130">IMsgServiceAdmin::DeleteMsgService</span><span class="sxs-lookup"><span data-stu-id="c846c-130">IMsgServiceAdmin::DeleteMsgService</span></span>](imsgserviceadmin-deletemsgservice.md)
  
[<span data-ttu-id="c846c-131">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c846c-131">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="c846c-132">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c846c-132">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

