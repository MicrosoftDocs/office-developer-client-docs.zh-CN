---
title: 磁盘实例和缓存表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d556ff4d-e2f3-4c83-a93f-b1bfda5abc8c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 27b21162c53a64675abbf31a8ab512719b413d5f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583160"
---
# <a name="disk-instances-and-cache-tables"></a><span data-ttu-id="4c718-103">磁盘实例和缓存表</span><span class="sxs-lookup"><span data-stu-id="4c718-103">Disk Instances and Cache Tables</span></span>

<span data-ttu-id="4c718-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4c718-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4c718-105">若要激活窗体，其可执行文件必须在用户的计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="4c718-105">To activate a form, its executable files must be available on the user's computer.</span></span> <span data-ttu-id="4c718-106">如果它们不可用，它们必须将复制从表单库到本地磁盘。</span><span class="sxs-lookup"><span data-stu-id="4c718-106">If they are not available, they must be copied from the form library to the local disk.</span></span> <span data-ttu-id="4c718-107">若要执行此操作，默认窗体管理器子目录中创建要包含窗体的可执行文件的用户的 Windows 目录 (。Exe。HLPs)。</span><span class="sxs-lookup"><span data-stu-id="4c718-107">To do this, the default form manager creates a subdirectory in the user's Windows directory to contain the form's executable files (.EXEs,.HLPs).</span></span> <span data-ttu-id="4c718-108">此目录称为窗体的磁盘实例。</span><span class="sxs-lookup"><span data-stu-id="4c718-108">This directory is referred to as the disk instance of the form.</span></span>
  
<span data-ttu-id="4c718-109">默认窗体管理器维护所有磁盘实例的一个表，以便如果磁盘实例已存在它可使用而无需从表单库的文件复制到用户的磁盘。</span><span class="sxs-lookup"><span data-stu-id="4c718-109">The default form manager maintains a table of all disk instances so that if a disk instance already exists it can be used without having to copy files from the form library to the user's disk.</span></span> <span data-ttu-id="4c718-110">作为最常用于高速缓存管理磁盘实例的表。</span><span class="sxs-lookup"><span data-stu-id="4c718-110">The table of disk instances is managed as a least-frequently-used cache.</span></span> <span data-ttu-id="4c718-111">如果需要新的磁盘实例时，它被复制到用户的计算机，替换的最常用于磁盘实例。</span><span class="sxs-lookup"><span data-stu-id="4c718-111">If a new disk instance is needed, it is copied to the user's computer, replacing the least-frequently-used disk instance.</span></span> <span data-ttu-id="4c718-112">磁盘实例缓存表然后将更新以反映的最新的配置。</span><span class="sxs-lookup"><span data-stu-id="4c718-112">The disk instance cache table is then updated to reflect the latest configuration.</span></span> <span data-ttu-id="4c718-113">磁盘缓存的大小是用户配置的选项，使用户能够可用磁盘容量平衡速度。</span><span class="sxs-lookup"><span data-stu-id="4c718-113">The size of the disk cache is a user-configurable option, enabling users to balance speed with available disk capacity.</span></span>
  
<span data-ttu-id="4c718-114">磁盘实例缓存，除了默认窗体管理器维护一个运行的实例表，用于列出所有正在运行的用户的计算机上的窗体服务器实例。</span><span class="sxs-lookup"><span data-stu-id="4c718-114">In addition to the disk instance cache, the default form manager maintains a running instance table that lists all running instances of form servers on the user's computer.</span></span> <span data-ttu-id="4c718-115">这将使用 MAPI 的能力保留空闲表单实例运行不可见状态，直到窗体的窗体激活类的服务器的消息。</span><span class="sxs-lookup"><span data-stu-id="4c718-115">This uses MAPI's ability to keep idle form instances running in an invisible state until a form of that form server's message class is activated.</span></span> <span data-ttu-id="4c718-116">换句话说，窗体服务器可以缓存在 RAM 中以最小化的表单的可执行文件必须位于表单库中并加载到内存中从磁盘或通过网络的次数。</span><span class="sxs-lookup"><span data-stu-id="4c718-116">In other words, form servers can be cached in RAM to minimize the number of times a form's executable must be located within a form library and loaded into memory from disk or over the network.</span></span> <span data-ttu-id="4c718-117">磁盘实例缓存，如正在运行的实例缓存行为以最常用于方式，以便运行窗体实例可以清除从缓存的另一个窗体实例留出空间。</span><span class="sxs-lookup"><span data-stu-id="4c718-117">Like the disk instance cache, the running instance cache behaves in a least-frequently-used fashion so that a running form instance can be purged from the cache to make room for another form instance.</span></span> <span data-ttu-id="4c718-118">表单库的搜索表单服务器之前，此缓存被搜索的窗体服务器正在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="4c718-118">This cache is searched for a running instance of a form server before the form libraries are searched for the form server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c718-119">默认窗体管理器显示进度指示器在用户的工作站上安装窗体时使用户可以取消操作。</span><span class="sxs-lookup"><span data-stu-id="4c718-119">The default form manager displays a progress indicator when installing a form on a user's workstation, enabling the user to cancel the operation.</span></span> <span data-ttu-id="4c718-120">这是通过低带宽网络与窗体服务器的可执行文件的用户的连接是否特别有用。</span><span class="sxs-lookup"><span data-stu-id="4c718-120">This is especially useful if the user's connection to the form server's executable file is over a low bandwidth network.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4c718-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c718-121">See also</span></span>

- [<span data-ttu-id="4c718-122">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="4c718-122">MAPI Forms</span></span>](mapi-forms.md)

