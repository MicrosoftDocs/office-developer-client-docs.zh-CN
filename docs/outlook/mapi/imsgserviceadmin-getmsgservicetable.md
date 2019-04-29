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
# <a name="imsgserviceadmingetmsgservicetable"></a><span data-ttu-id="1d5ed-103">IMsgServiceAdmin::GetMsgServiceTable</span><span class="sxs-lookup"><span data-stu-id="1d5ed-103">IMsgServiceAdmin::GetMsgServiceTable</span></span>

  
  
<span data-ttu-id="1d5ed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1d5ed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1d5ed-105">提供对邮件服务表 (配置文件中的邮件服务列表) 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-105">Provides access to the message service table, a list of the message services in the profile.</span></span>
  
```cpp
HRESULT GetMsgServiceTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="1d5ed-106">参数</span><span class="sxs-lookup"><span data-stu-id="1d5ed-106">Parameters</span></span>

 <span data-ttu-id="1d5ed-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1d5ed-107">_ulFlags_</span></span>
  
> <span data-ttu-id="1d5ed-108">实时始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="1d5ed-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="1d5ed-109">_lppTable_</span></span>
  
> <span data-ttu-id="1d5ed-110">排除指向邮件服务表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-110">[out] A pointer to a pointer to the message service table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1d5ed-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1d5ed-111">Return value</span></span>

<span data-ttu-id="1d5ed-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d5ed-112">S_OK</span></span> 
  
> <span data-ttu-id="1d5ed-113">成功返回邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-113">The message service table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1d5ed-114">说明</span><span class="sxs-lookup"><span data-stu-id="1d5ed-114">Remarks</span></span>

<span data-ttu-id="1d5ed-115">**IMsgServiceAdmin:: GetMsgServiceTable**方法提供对邮件服务表的访问, MAPI 维护的表列出了当前安装在会话配置文件中的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-115">The **IMsgServiceAdmin::GetMsgServiceTable** method provides access to the message service table, a table that MAPI maintains that lists the message services currently installed in the session profile.</span></span> <span data-ttu-id="1d5ed-116">有关邮件服务表中的列的完整列表, 请参阅[message service 表](message-service-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-116">For a complete list of columns in the message service table, see [Message Service Table](message-service-tables.md).</span></span>
  
<span data-ttu-id="1d5ed-117">邮件服务表是静态的。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-117">The message service table is static.</span></span> <span data-ttu-id="1d5ed-118">客户端被授予访问权限后, 后续的邮件服务添加或删除操作不会影响它。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-118">After a client has been given access to it, subsequent message service additions or deletions will not affect it.</span></span> <span data-ttu-id="1d5ed-119">如果当前配置文件中没有任何邮件服务, **GetMsgServiceTable**将返回一个包含零行的表。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-119">If there are no message services in the current profile, **GetMsgServiceTable** returns a table with zero rows.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1d5ed-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="1d5ed-120">MFCMAPI reference</span></span>

<span data-ttu-id="1d5ed-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1d5ed-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="1d5ed-122">**File**</span></span>|<span data-ttu-id="1d5ed-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="1d5ed-123">**Function**</span></span>|<span data-ttu-id="1d5ed-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="1d5ed-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d5ed-125">MsgServiceTableDlg</span><span class="sxs-lookup"><span data-stu-id="1d5ed-125">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="1d5ed-126">CMsgServiceTableDlg:: OnRefreshView</span><span class="sxs-lookup"><span data-stu-id="1d5ed-126">CMsgServiceTableDlg::OnRefreshView</span></span>  <br/> |<span data-ttu-id="1d5ed-127">MFCMAPI 使用**IMsgServiceAdmin:: GetMsgServiceTable**方法加载要在视图中呈现的配置文件中的服务表。</span><span class="sxs-lookup"><span data-stu-id="1d5ed-127">MFCMAPI uses the **IMsgServiceAdmin::GetMsgServiceTable** method to load the table of services in a profile to render in the view.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1d5ed-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d5ed-128">See also</span></span>



[<span data-ttu-id="1d5ed-129">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="1d5ed-129">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="1d5ed-130">IMsgServiceAdmin::DeleteMsgService</span><span class="sxs-lookup"><span data-stu-id="1d5ed-130">IMsgServiceAdmin::DeleteMsgService</span></span>](imsgserviceadmin-deletemsgservice.md)
  
[<span data-ttu-id="1d5ed-131">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1d5ed-131">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="1d5ed-132">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1d5ed-132">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

