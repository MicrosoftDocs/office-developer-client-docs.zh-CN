---
title: PROP_ACCT_PREFERENCES_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ec0aac33-624e-48f7-8177-8f7b8db6af7d
description: 检索存储的帐户首选项配置文件一节的唯一标识符 (UID)。
ms.openlocfilehash: 70e61264e5525f26e9f52e402bc785b544a0b90e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774441"
---
# <a name="propacctpreferencesuid"></a><span data-ttu-id="149a8-103">PROP_ACCT_PREFERENCES_UID</span><span class="sxs-lookup"><span data-stu-id="149a8-103">PROP_ACCT_PREFERENCES_UID</span></span>

<span data-ttu-id="149a8-104">检索存储的帐户首选项配置文件一节的唯一标识符 (UID)。</span><span class="sxs-lookup"><span data-stu-id="149a8-104">Retrieves the unique identifier (UID) for the profile section that stores the account preferences.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="149a8-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="149a8-105">Quick info</span></span>

<span data-ttu-id="149a8-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="149a8-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="149a8-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="149a8-107">Identifier:</span></span>  <br/> |<span data-ttu-id="149a8-108">0x0022</span><span class="sxs-lookup"><span data-stu-id="149a8-108">0x0022</span></span>  <br/> |
|<span data-ttu-id="149a8-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="149a8-109">Property type:</span></span>  <br/> |<span data-ttu-id="149a8-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="149a8-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="149a8-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="149a8-111">Property tag:</span></span>  <br/> |<span data-ttu-id="149a8-112">0x00220102</span><span class="sxs-lookup"><span data-stu-id="149a8-112">0x00220102</span></span>  <br/> |
|<span data-ttu-id="149a8-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="149a8-113">Access:</span></span>  <br/> |<span data-ttu-id="149a8-114">只读</span><span class="sxs-lookup"><span data-stu-id="149a8-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="149a8-115">说明</span><span class="sxs-lookup"><span data-stu-id="149a8-115">Remarks</span></span>

<span data-ttu-id="149a8-116">使用中调用[IMAPISupport::OpenProfileSection](http://msdn.microsoft.com/library/cd1fa994-9531-46c4-94e5-505e7f90b884%28Office.15%29.aspx) **PROP_ACCT_PREFERENCES_UID**检索包含帐户首选项配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="149a8-116">Use **PROP_ACCT_PREFERENCES_UID** in calls to [IMAPISupport::OpenProfileSection](http://msdn.microsoft.com/library/cd1fa994-9531-46c4-94e5-505e7f90b884%28Office.15%29.aspx) to retrieve the profile section that contains account preferences.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="149a8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="149a8-117">See also</span></span>

- [<span data-ttu-id="149a8-118">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="149a8-118">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="149a8-119">有关反垃圾邮件设置</span><span class="sxs-lookup"><span data-stu-id="149a8-119">About anti-spam settings</span></span>](about-anti-spam-settings.md)

