---
title: 关于 MAPI 崩溃恢复 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: bc1e1f55-1959-a4a9-a24d-f006af531c9a
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: fbb6d22414daf3464e80fbf1d9cf92ccb3d560e3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576587"
---
# <a name="about-the-mapi-crash-recovery-api"></a><span data-ttu-id="a2165-103">关于 MAPI 崩溃恢复 API</span><span class="sxs-lookup"><span data-stu-id="a2165-103">About the MAPI Crash Recovery API</span></span>

  
  
<span data-ttu-id="a2165-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2165-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2165-105">MAPI 崩溃恢复 API 检查个人文件夹文件 (PST) 或脱机文件夹 (OST) 文件的状态共享内存来验证数据处于一致状态。</span><span class="sxs-lookup"><span data-stu-id="a2165-105">The MAPI Crash Recovery API checks the state of the Personal Folders file (PST) or Offline Folders file (OST) shared memory to verify that the data is in a consistent state.</span></span> <span data-ttu-id="a2165-106">如果是处于一致状态，则会将数据从打开的 Pst 或 Ost 移到磁盘上锁定 Pst 或 Ost [MAPICrashRecovery](mapicrashrecovery.md)函数并将其不允许任何读取或写入访问数据。</span><span class="sxs-lookup"><span data-stu-id="a2165-106">If it is in a consistent state, the [MAPICrashRecovery](mapicrashrecovery.md) function moves the data from the open PSTs or OSTs to disk and locks the PSTs or OSTs and does not allow any read or write access to the data.</span></span> <span data-ttu-id="a2165-107">这样可确保终止过程之前的数据保持一致状态。</span><span class="sxs-lookup"><span data-stu-id="a2165-107">This ensures that the data remains in a consistent state until the process is terminated.</span></span> <span data-ttu-id="a2165-108">通过确保 Pst 或 Ost 处于一致状态终止过程之前，您可以禁止 Microsoft Outlook 2013 和 Microsoft Outlook 2010 中显示以下错误消息，并避免性能问题。</span><span class="sxs-lookup"><span data-stu-id="a2165-108">By ensuring that the PSTs or OSTs are in a consistent state before the process is terminated, you can prevent Microsoft Outlook 2013 and Microsoft Outlook 2010 from displaying the following error message and avoid performance problems.</span></span> 
  
 <span data-ttu-id="a2165-109">**数据文件未无法正确关闭问题上次用，并且正在签。正在检查时，可能会影响性能。**</span><span class="sxs-lookup"><span data-stu-id="a2165-109">**A data file did not close properly the last time it was used and is being checked for problems. Performance might be affected while the check is in progress.**</span></span>
  
<span data-ttu-id="a2165-110">此 API 提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="a2165-110">This API provides the following:</span></span>
  
<span data-ttu-id="a2165-111">常量：</span><span class="sxs-lookup"><span data-stu-id="a2165-111">Constants:</span></span>
  
- [<span data-ttu-id="a2165-112">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="a2165-112">MAPI Constants</span></span>](mapi-constants.md)
    
<span data-ttu-id="a2165-113">函数：</span><span class="sxs-lookup"><span data-stu-id="a2165-113">Functions:</span></span>
  
- [<span data-ttu-id="a2165-114">MAPICrashRecovery</span><span class="sxs-lookup"><span data-stu-id="a2165-114">MAPICrashRecovery</span></span>](mapicrashrecovery.md)
    
## <a name="see-also"></a><span data-ttu-id="a2165-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2165-115">See also</span></span>



[<span data-ttu-id="a2165-116">使用 MAPI 崩溃恢复 API</span><span class="sxs-lookup"><span data-stu-id="a2165-116">Use the MAPI Crash Recovery API</span></span>](how-to-use-the-mapi-crash-recovery-api.md)

