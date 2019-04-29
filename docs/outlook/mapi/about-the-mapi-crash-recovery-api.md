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
# <a name="about-the-mapi-crash-recovery-api"></a><span data-ttu-id="73886-103">关于 MAPI 故障恢复 API</span><span class="sxs-lookup"><span data-stu-id="73886-103">About the MAPI Crash Recovery API</span></span>

  
  
<span data-ttu-id="73886-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="73886-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="73886-105">MAPI 故障恢复 API 检查个人文件夹文件 (PST) 或脱机文件夹文件 (OST) 共享内存的状态, 以验证数据是否处于一致状态。</span><span class="sxs-lookup"><span data-stu-id="73886-105">The MAPI Crash Recovery API checks the state of the Personal Folders file (PST) or Offline Folders file (OST) shared memory to verify that the data is in a consistent state.</span></span> <span data-ttu-id="73886-106">如果处于 "一致" 状态, 则[MAPICrashRecovery](mapicrashrecovery.md)函数会将数据从打开的 pst 或 OSTs 移动到磁盘, 并锁定 pst 或 OSTs, 并且不允许对数据进行任何读取或写入访问。</span><span class="sxs-lookup"><span data-stu-id="73886-106">If it is in a consistent state, the [MAPICrashRecovery](mapicrashrecovery.md) function moves the data from the open PSTs or OSTs to disk and locks the PSTs or OSTs and does not allow any read or write access to the data.</span></span> <span data-ttu-id="73886-107">这样可确保在进程终止之前, 数据保持一致状态。</span><span class="sxs-lookup"><span data-stu-id="73886-107">This ensures that the data remains in a consistent state until the process is terminated.</span></span> <span data-ttu-id="73886-108">通过确保 pst 或 OSTs 在进程终止之前处于一致状态, 您可以阻止 microsoft outlook 2013 和 microsoft outlook 2010 显示以下错误消息, 避免出现性能问题。</span><span class="sxs-lookup"><span data-stu-id="73886-108">By ensuring that the PSTs or OSTs are in a consistent state before the process is terminated, you can prevent Microsoft Outlook 2013 and Microsoft Outlook 2010 from displaying the following error message and avoid performance problems.</span></span> 
  
 <span data-ttu-id="73886-109">**上次使用数据文件时, 它未正确关闭, 且正在检查是否存在问题。在检查过程中, 性能可能会受到影响。**</span><span class="sxs-lookup"><span data-stu-id="73886-109">**A data file did not close properly the last time it was used and is being checked for problems. Performance might be affected while the check is in progress.**</span></span>
  
<span data-ttu-id="73886-110">此 API 提供以下内容:</span><span class="sxs-lookup"><span data-stu-id="73886-110">This API provides the following:</span></span>
  
<span data-ttu-id="73886-111">称作</span><span class="sxs-lookup"><span data-stu-id="73886-111">Constants:</span></span>
  
- [<span data-ttu-id="73886-112">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="73886-112">MAPI Constants</span></span>](mapi-constants.md)
    
<span data-ttu-id="73886-113">函数：</span><span class="sxs-lookup"><span data-stu-id="73886-113">Functions:</span></span>
  
- [<span data-ttu-id="73886-114">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="73886-114">MAPICrashRecovery</span></span>](mapicrashrecovery.md)
    
## <a name="see-also"></a><span data-ttu-id="73886-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73886-115">See also</span></span>



[<span data-ttu-id="73886-116">使用 MAPI 故障恢复 API</span><span class="sxs-lookup"><span data-stu-id="73886-116">Use the MAPI Crash Recovery API</span></span>](how-to-use-the-mapi-crash-recovery-api.md)

