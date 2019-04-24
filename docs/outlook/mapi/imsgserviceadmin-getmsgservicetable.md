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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309973"
---
# <a name="imsgserviceadmingetmsgservicetable"></a><span data-ttu-id="69282-103">IMsgServiceAdmin::GetMsgServiceTable</span><span class="sxs-lookup"><span data-stu-id="69282-103">IMsgServiceAdmin::GetMsgServiceTable</span></span>

  
  
<span data-ttu-id="69282-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="69282-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="69282-105">提供对邮件服务表 (配置文件中的邮件服务列表) 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="69282-105">Provides access to the message service table, a list of the message services in the profile.</span></span>
  
```cpp
HRESULT GetMsgServiceTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="69282-106">参数</span><span class="sxs-lookup"><span data-stu-id="69282-106">Parameters</span></span>

 <span data-ttu-id="69282-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="69282-107">_ulFlags_</span></span>
  
> <span data-ttu-id="69282-108">实时始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="69282-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="69282-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="69282-109">_lppTable_</span></span>
  
> <span data-ttu-id="69282-110">排除指向邮件服务表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="69282-110">[out] A pointer to a pointer to the message service table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="69282-111">返回值</span><span class="sxs-lookup"><span data-stu-id="69282-111">Return value</span></span>

<span data-ttu-id="69282-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="69282-112">S_OK</span></span> 
  
> <span data-ttu-id="69282-113">成功返回邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="69282-113">The message service table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="69282-114">注解</span><span class="sxs-lookup"><span data-stu-id="69282-114">Remarks</span></span>

<span data-ttu-id="69282-115">**IMsgServiceAdmin:: GetMsgServiceTable**方法提供对邮件服务表的访问, MAPI 维护的表列出了当前安装在会话配置文件中的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="69282-115">The **IMsgServiceAdmin::GetMsgServiceTable** method provides access to the message service table, a table that MAPI maintains that lists the message services currently installed in the session profile.</span></span> <span data-ttu-id="69282-116">有关邮件服务表中的列的完整列表, 请参阅[message service 表](message-service-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="69282-116">For a complete list of columns in the message service table, see [Message Service Table](message-service-tables.md).</span></span>
  
<span data-ttu-id="69282-117">邮件服务表是静态的。</span><span class="sxs-lookup"><span data-stu-id="69282-117">The message service table is static.</span></span> <span data-ttu-id="69282-118">客户端被授予访问权限后, 后续的邮件服务添加或删除操作不会影响它。</span><span class="sxs-lookup"><span data-stu-id="69282-118">After a client has been given access to it, subsequent message service additions or deletions will not affect it.</span></span> <span data-ttu-id="69282-119">如果当前配置文件中没有任何邮件服务, **GetMsgServiceTable**将返回一个包含零行的表。</span><span class="sxs-lookup"><span data-stu-id="69282-119">If there are no message services in the current profile, **GetMsgServiceTable** returns a table with zero rows.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="69282-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="69282-120">MFCMAPI reference</span></span>

<span data-ttu-id="69282-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="69282-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="69282-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="69282-122">**File**</span></span>|<span data-ttu-id="69282-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="69282-123">**Function**</span></span>|<span data-ttu-id="69282-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="69282-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69282-125">MsgServiceTableDlg</span><span class="sxs-lookup"><span data-stu-id="69282-125">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="69282-126">CMsgServiceTableDlg:: OnRefreshView</span><span class="sxs-lookup"><span data-stu-id="69282-126">CMsgServiceTableDlg::OnRefreshView</span></span>  <br/> |<span data-ttu-id="69282-127">MFCMAPI 使用**IMsgServiceAdmin:: GetMsgServiceTable**方法加载要在视图中呈现的配置文件中的服务表。</span><span class="sxs-lookup"><span data-stu-id="69282-127">MFCMAPI uses the **IMsgServiceAdmin::GetMsgServiceTable** method to load the table of services in a profile to render in the view.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="69282-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69282-128">See also</span></span>



[<span data-ttu-id="69282-129">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="69282-129">IMsgServiceAdmin::ConfigureMsgService</span></span>](imsgserviceadmin-configuremsgservice.md)
  
[<span data-ttu-id="69282-130">IMsgServiceAdmin::DeleteMsgService</span><span class="sxs-lookup"><span data-stu-id="69282-130">IMsgServiceAdmin::DeleteMsgService</span></span>](imsgserviceadmin-deletemsgservice.md)
  
[<span data-ttu-id="69282-131">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="69282-131">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="69282-132">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="69282-132">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

