---
title: PROP_ACCT_PREFERENCES_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ec0aac33-624e-48f7-8177-8f7b8db6af7d
description: 检索存储帐户首选项的 "配置文件" 部分的唯一标识符 (UID)。
ms.openlocfilehash: 97f1a858c8f58e13b72b8d5f052b35359581b718
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327634"
---
# <a name="propacctpreferencesuid"></a><span data-ttu-id="2a343-103">PROP_ACCT_PREFERENCES_UID</span><span class="sxs-lookup"><span data-stu-id="2a343-103">PROP_ACCT_PREFERENCES_UID</span></span>

<span data-ttu-id="2a343-104">检索存储帐户首选项的 "配置文件" 部分的唯一标识符 (UID)。</span><span class="sxs-lookup"><span data-stu-id="2a343-104">Retrieves the unique identifier (UID) for the profile section that stores the account preferences.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="2a343-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="2a343-105">Quick info</span></span>

<span data-ttu-id="2a343-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="2a343-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2a343-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="2a343-107">Identifier:</span></span>  <br/> |<span data-ttu-id="2a343-108">0x0022</span><span class="sxs-lookup"><span data-stu-id="2a343-108">0x0022</span></span>  <br/> |
|<span data-ttu-id="2a343-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="2a343-109">Property type:</span></span>  <br/> |<span data-ttu-id="2a343-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2a343-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2a343-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="2a343-111">Property tag:</span></span>  <br/> |<span data-ttu-id="2a343-112">0x00220102</span><span class="sxs-lookup"><span data-stu-id="2a343-112">0x00220102</span></span>  <br/> |
|<span data-ttu-id="2a343-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="2a343-113">Access:</span></span>  <br/> |<span data-ttu-id="2a343-114">只读</span><span class="sxs-lookup"><span data-stu-id="2a343-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2a343-115">注解</span><span class="sxs-lookup"><span data-stu-id="2a343-115">Remarks</span></span>

<span data-ttu-id="2a343-116">在调用[IMAPISupport:: OpenProfileSection](https://msdn.microsoft.com/library/cd1fa994-9531-46c4-94e5-505e7f90b884%28Office.15%29.aspx)以检索包含帐户首选项的 profile 节时, 请使用**PROP_ACCT_PREFERENCES_UID** 。</span><span class="sxs-lookup"><span data-stu-id="2a343-116">Use **PROP_ACCT_PREFERENCES_UID** in calls to [IMAPISupport::OpenProfileSection](https://msdn.microsoft.com/library/cd1fa994-9531-46c4-94e5-505e7f90b884%28Office.15%29.aspx) to retrieve the profile section that contains account preferences.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2a343-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a343-117">See also</span></span>

- [<span data-ttu-id="2a343-118">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="2a343-118">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="2a343-119">有关反垃圾邮件设置</span><span class="sxs-lookup"><span data-stu-id="2a343-119">About anti-spam settings</span></span>](about-anti-spam-settings.md)

