---
title: 关于 MAPI 故障恢复 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: bc1e1f55-1959-a4a9-a24d-f006af531c9a
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 1acca6d806c1734007ac7c5e41059d3a870dc5bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420260"
---
# <a name="about-the-mapi-crash-recovery-api"></a><span data-ttu-id="2632b-103">关于 MAPI 故障恢复 API</span><span class="sxs-lookup"><span data-stu-id="2632b-103">About the MAPI Crash Recovery API</span></span>

  
  
<span data-ttu-id="2632b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2632b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2632b-105">MAPI 故障恢复 API 检查个人文件夹文件 (PST) 或脱机文件夹文件 (OST) 共享内存的状态，以验证数据是否处于一致状态。</span><span class="sxs-lookup"><span data-stu-id="2632b-105">The MAPI Crash Recovery API checks the state of the Personal Folders file (PST) or Offline Folders file (OST) shared memory to verify that the data is in a consistent state.</span></span> <span data-ttu-id="2632b-106">如果状态一致 [，MAPICrashRecovery](mapicrashrecovery.md) 函数会将数据从打开的 PST 或 OST 移动到磁盘，并锁定 PST 或 OST，并且不允许对数据进行任何读或写访问。</span><span class="sxs-lookup"><span data-stu-id="2632b-106">If it is in a consistent state, the [MAPICrashRecovery](mapicrashrecovery.md) function moves the data from the open PSTs or OSTs to disk and locks the PSTs or OSTs and does not allow any read or write access to the data.</span></span> <span data-ttu-id="2632b-107">这将确保数据保持一致状态，直到进程终止。</span><span class="sxs-lookup"><span data-stu-id="2632b-107">This ensures that the data remains in a consistent state until the process is terminated.</span></span> <span data-ttu-id="2632b-108">通过确保在终止进程之前，PST 或 OST 保持一致状态，可以防止 Microsoft Outlook 2013 和 Microsoft Outlook 2010 显示以下错误消息，并避免性能问题。</span><span class="sxs-lookup"><span data-stu-id="2632b-108">By ensuring that the PSTs or OSTs are in a consistent state before the process is terminated, you can prevent Microsoft Outlook 2013 and Microsoft Outlook 2010 from displaying the following error message and avoid performance problems.</span></span> 
  
 <span data-ttu-id="2632b-109">**上次使用数据文件时未正确关闭，并且正在检查是否出现问题。正在进行检查时，性能可能会受到影响。**</span><span class="sxs-lookup"><span data-stu-id="2632b-109">**A data file did not close properly the last time it was used and is being checked for problems. Performance might be affected while the check is in progress.**</span></span>
  
<span data-ttu-id="2632b-110">此 API 提供以下内容：</span><span class="sxs-lookup"><span data-stu-id="2632b-110">This API provides the following:</span></span>
  
<span data-ttu-id="2632b-111">常量：</span><span class="sxs-lookup"><span data-stu-id="2632b-111">Constants:</span></span>
  
- [<span data-ttu-id="2632b-112">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2632b-112">MAPI Constants</span></span>](mapi-constants.md)
    
<span data-ttu-id="2632b-113">函数：</span><span class="sxs-lookup"><span data-stu-id="2632b-113">Functions:</span></span>
  
- [<span data-ttu-id="2632b-114">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="2632b-114">MAPICrashRecovery</span></span>](mapicrashrecovery.md)
    
## <a name="see-also"></a><span data-ttu-id="2632b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2632b-115">See also</span></span>



[<span data-ttu-id="2632b-116">使用 MAPI 故障恢复 API</span><span class="sxs-lookup"><span data-stu-id="2632b-116">Use the MAPI Crash Recovery API</span></span>](how-to-use-the-mapi-crash-recovery-api.md)

