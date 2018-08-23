---
title: IOlkErrorUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9cfbf12c-a71c-092b-d86a-c5585b0f1edb
ms.openlocfilehash: 311d055e0a319ec26cdc4eba5ac3b50dc9e63d9d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565177"
---
# <a name="iolkerrorunknown"></a><span data-ttu-id="83704-102">IOlkErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="83704-102">IOlkErrorUnknown</span></span>

<span data-ttu-id="83704-103">提供有关最后一个错误的额外信息。</span><span class="sxs-lookup"><span data-stu-id="83704-103">Provides extra information about the last error.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="83704-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="83704-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="83704-105">继承：</span><span class="sxs-lookup"><span data-stu-id="83704-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="83704-106">IUnknown</span><span class="sxs-lookup"><span data-stu-id="83704-106">IUnknown</span></span>](https://docs.microsoft.com/en-us/windows/desktop/api/unknwn/nn-unknwn-iunknown) <br/> |
|<span data-ttu-id="83704-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="83704-107">Provided by:</span></span>  <br/> |<span data-ttu-id="83704-108">客户端</span><span class="sxs-lookup"><span data-stu-id="83704-108">Client</span></span>  <br/> |
|<span data-ttu-id="83704-109">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="83704-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="83704-110">IID_IOlkErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="83704-110">IID_IOlkErrorUnknown</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="83704-111">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="83704-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="83704-112">时出错</span><span class="sxs-lookup"><span data-stu-id="83704-112">GetLastError</span></span>](iolkerrorunknown-getlasterror.md) <br/> |<span data-ttu-id="83704-113">获取指定的错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="83704-113">Gets a message string for the specified error.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="83704-114">注解</span><span class="sxs-lookup"><span data-stu-id="83704-114">Remarks</span></span>

<span data-ttu-id="83704-115">此接口提供了有关[IOlkAccountManager](iolkaccountmanager.md)、 [IOlkAccountNotify](iolkaccountnotify.md)和[IOlkAccount](iolkaccount.md)中的错误的额外信息。</span><span class="sxs-lookup"><span data-stu-id="83704-115">This interface provides extra information about an error in [IOlkAccountManager](iolkaccountmanager.md), [IOlkAccountNotify](iolkaccountnotify.md), and [IOlkAccount](iolkaccount.md).</span></span> <span data-ttu-id="83704-116">它也是**IOlkAccountManager**、 **IOlkAccountNotify**和**IOlkAccount**的基接口。</span><span class="sxs-lookup"><span data-stu-id="83704-116">It is also the base interface for **IOlkAccountManager**, **IOlkAccountNotify**, and **IOlkAccount**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="83704-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83704-117">See also</span></span>

- [<span data-ttu-id="83704-118">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="83704-118">About the Account Management API</span></span>](about-the-account-management-api.md)

