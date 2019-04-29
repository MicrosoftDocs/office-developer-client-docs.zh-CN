---
title: 磁盘实例和缓存表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d556ff4d-e2f3-4c83-a93f-b1bfda5abc8c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4f0b66476b1ab3d149b6f7e7b8171de7a509b597
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436753"
---
# <a name="disk-instances-and-cache-tables"></a><span data-ttu-id="8a8da-103">磁盘实例和缓存表</span><span class="sxs-lookup"><span data-stu-id="8a8da-103">Disk Instances and Cache Tables</span></span>

<span data-ttu-id="8a8da-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a8da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a8da-105">若要激活窗体, 其可执行文件必须在用户的计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="8a8da-105">To activate a form, its executable files must be available on the user's computer.</span></span> <span data-ttu-id="8a8da-106">如果它们不可用, 则必须将它们从表单库复制到本地磁盘。</span><span class="sxs-lookup"><span data-stu-id="8a8da-106">If they are not available, they must be copied from the form library to the local disk.</span></span> <span data-ttu-id="8a8da-107">若要执行此操作, 默认表单管理器会在用户的 Windows 目录中创建一个子目录, 以包含该表单的可执行文件 (。exe。HLPs)。</span><span class="sxs-lookup"><span data-stu-id="8a8da-107">To do this, the default form manager creates a subdirectory in the user's Windows directory to contain the form's executable files (.EXEs,.HLPs).</span></span> <span data-ttu-id="8a8da-108">此目录称为表单的磁盘实例。</span><span class="sxs-lookup"><span data-stu-id="8a8da-108">This directory is referred to as the disk instance of the form.</span></span>
  
<span data-ttu-id="8a8da-109">默认表单管理器维护所有磁盘实例的表, 以便在已存在磁盘实例时可以使用该实例, 而无需将文件从表单库复制到用户磁盘。</span><span class="sxs-lookup"><span data-stu-id="8a8da-109">The default form manager maintains a table of all disk instances so that if a disk instance already exists it can be used without having to copy files from the form library to the user's disk.</span></span> <span data-ttu-id="8a8da-110">磁盘实例表是作为最常用的缓存进行管理。</span><span class="sxs-lookup"><span data-stu-id="8a8da-110">The table of disk instances is managed as a least-frequently-used cache.</span></span> <span data-ttu-id="8a8da-111">如果需要新的磁盘实例, 则会将其复制到用户的计算机上, 以替换最常用的磁盘实例。</span><span class="sxs-lookup"><span data-stu-id="8a8da-111">If a new disk instance is needed, it is copied to the user's computer, replacing the least-frequently-used disk instance.</span></span> <span data-ttu-id="8a8da-112">然后更新磁盘实例缓存表以反映最新的配置。</span><span class="sxs-lookup"><span data-stu-id="8a8da-112">The disk instance cache table is then updated to reflect the latest configuration.</span></span> <span data-ttu-id="8a8da-113">磁盘缓存的大小是一个用户可配置的选项, 使用户能够以更高的速度平衡可用磁盘容量。</span><span class="sxs-lookup"><span data-stu-id="8a8da-113">The size of the disk cache is a user-configurable option, enabling users to balance speed with available disk capacity.</span></span>
  
<span data-ttu-id="8a8da-114">除了磁盘实例缓存之外, 默认表单管理器还维护一个正在运行的实例表, 该表列出了用户计算机上所有正在运行的表单服务器实例。</span><span class="sxs-lookup"><span data-stu-id="8a8da-114">In addition to the disk instance cache, the default form manager maintains a running instance table that lists all running instances of form servers on the user's computer.</span></span> <span data-ttu-id="8a8da-115">这将使用 MAPI 将空闲表单实例保持在不可见状态中运行, 直到窗体服务器的邮件类的窗体被激活。</span><span class="sxs-lookup"><span data-stu-id="8a8da-115">This uses MAPI's ability to keep idle form instances running in an invisible state until a form of that form server's message class is activated.</span></span> <span data-ttu-id="8a8da-116">换句话说, 表单服务器可以缓存在内存中, 以最大限度地减少表单可执行文件在表单库中的的次数, 并从磁盘或网络中加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="8a8da-116">In other words, form servers can be cached in RAM to minimize the number of times a form's executable must be located within a form library and loaded into memory from disk or over the network.</span></span> <span data-ttu-id="8a8da-117">与磁盘实例缓存一样, 正在运行的实例缓存的行为方式最少, 因此可以从缓存中清除正在运行的窗体实例, 以便为另一个窗体实例留出空间。</span><span class="sxs-lookup"><span data-stu-id="8a8da-117">Like the disk instance cache, the running instance cache behaves in a least-frequently-used fashion so that a running form instance can be purged from the cache to make room for another form instance.</span></span> <span data-ttu-id="8a8da-118">在表单库在表单库中搜索表单库之前, 将在此缓存中搜索运行的表单服务器实例。</span><span class="sxs-lookup"><span data-stu-id="8a8da-118">This cache is searched for a running instance of a form server before the form libraries are searched for the form server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a8da-119">默认表单管理器在用户的工作站上安装表单时显示一个进度指示器, 使用户可以取消该操作。</span><span class="sxs-lookup"><span data-stu-id="8a8da-119">The default form manager displays a progress indicator when installing a form on a user's workstation, enabling the user to cancel the operation.</span></span> <span data-ttu-id="8a8da-120">如果用户与表单服务器的可执行文件的连接是在低带宽网络上, 则此方法尤其有用。</span><span class="sxs-lookup"><span data-stu-id="8a8da-120">This is especially useful if the user's connection to the form server's executable file is over a low bandwidth network.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8a8da-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a8da-121">See also</span></span>

- [<span data-ttu-id="8a8da-122">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="8a8da-122">MAPI Forms</span></span>](mapi-forms.md)

