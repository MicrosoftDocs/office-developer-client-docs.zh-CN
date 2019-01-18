---
title: 确定 Outlook 是否是计算机上的即点即用应用程序
TOCTitle: Determine whether Outlook is a Click-to-Run application on a computer
ms:assetid: 1b8573be-8ea8-4973-869d-87fda57ce525
ms:mtpsurl: https://msdn.microsoft.com/library/Ff522355(v=office.15)
ms:contentKeyID: 55119804
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4a710baa4d70ac69b67d2a06fe694998884fd835
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717634"
---
# <a name="determine-whether-outlook-is-a-click-to-run-application-on-a-computer"></a><span data-ttu-id="7f960-102">确定 Outlook 是否是计算机上的即点即用应用程序</span><span class="sxs-lookup"><span data-stu-id="7f960-102">Determine whether Outlook is a Click-to-Run application on a computer</span></span>

<span data-ttu-id="7f960-103">即点即用是一种适用于 Office 2010 及更高版本的软件分发和更新机制。</span><span class="sxs-lookup"><span data-stu-id="7f960-103">Click-to-Run is a software delivery and updating mechanism available to Office 2010 and later versions.</span></span> <span data-ttu-id="7f960-104">通过即点即用分发的产品在本地操作系统上的虚拟应用程序环境中执行。</span><span class="sxs-lookup"><span data-stu-id="7f960-104">Products delivered via Click-to-Run execute in a virtual application environment on the local operating system.</span></span> <span data-ttu-id="7f960-105">这意味着这些产品具有其文件和设置的私有副本，并且它们所做的任何更改会在虚拟环境中捕获到。</span><span class="sxs-lookup"><span data-stu-id="7f960-105">This means that they have private copies of their files and settings, and that any changes they make are captured in the virtual environment.</span></span>

<span data-ttu-id="7f960-106">即点即用速度快，即表示用户在很短时间内就能开始运行应用程序，而不用等待完整产品完成安装。</span><span class="sxs-lookup"><span data-stu-id="7f960-106">Click-to-Run is fast—users can start running an application within a short time without waiting for the complete product to finish installing.</span></span> <span data-ttu-id="7f960-107">更新会在后台自动运行，无需用户首先移除安装或手动安装更新。</span><span class="sxs-lookup"><span data-stu-id="7f960-107">Updates are run automatically in the background, without requiring a user to first remove an installation or manually install updates.</span></span> <span data-ttu-id="7f960-108">即点即用产品进行了虚拟化，不会与其他已安装软件发生冲突。</span><span class="sxs-lookup"><span data-stu-id="7f960-108">Click-to-Run products are virtualized and do not conflict with other installed software.</span></span> <span data-ttu-id="7f960-109">不过，由于通过即点即用分发的产品有所有文件和注册的私有副本，因此加载项开发人员无法确定这种产品的存在方式是否与客户端计算机硬盘上已安装的产品相同。</span><span class="sxs-lookup"><span data-stu-id="7f960-109">However, because a product delivered by Click-to-Run has private copies of all its files and registration, an add-in developer cannot determine the product’s existence in the same manner as a product that was installed on a client computer’s hard disk.</span></span> <span data-ttu-id="7f960-110">自 Outlook 2010 起，加载项开发人员应验证是否已安装 Outlook，并验证 Outlook 是否已作为即点即用产品分发。</span><span class="sxs-lookup"><span data-stu-id="7f960-110">Starting with Outlook 2010, add-in developers should verify whether Outlook has been installed, and whether Outlook has been delivered as a Click-to-Run product.</span></span>


> [!NOTE]
> <span data-ttu-id="7f960-111">即使客户端计算机运行的是 64 位操作系统，即点即用虚拟应用程序环境中也仅支持 32 位的 Office 2013。</span><span class="sxs-lookup"><span data-stu-id="7f960-111">Only 32-bit Office 2013 is supported in the Click-to-Run virtual application environment, even if the client computer runs a 64-bit operating system.</span></span>



### <a name="to-check-whether-outlook-2013-was-delivered-by-click-to-run-on-a-client-computer"></a><span data-ttu-id="7f960-112">检查客户端计算机上的 Outlook 2013 是否是通过即点即用进行分发的具体步骤</span><span class="sxs-lookup"><span data-stu-id="7f960-112">To check whether Outlook 2013 was delivered by Click-to-Run on a client computer</span></span>

- <span data-ttu-id="7f960-113">验证 Windows 注册表中的以下位置上是否有 VirtualOutlook 键：</span><span class="sxs-lookup"><span data-stu-id="7f960-113">Verify whether the VirtualOutlook key exists in the following location in the Windows registry:</span></span>
    
  `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Office\15.0\Common\InstallRoot\Virtual\VirtualOutlook`
    
  <span data-ttu-id="7f960-114">VirtualOutlook 键是 REG\_SZ 值，其中包含已安装产品语言的区域性标记（如“en-us”）。</span><span class="sxs-lookup"><span data-stu-id="7f960-114">The VirtualOutlook key is a REG\_SZ value that contains the culture tag of the installed product language, such as "en-us".</span></span>

## <a name="see-also"></a><span data-ttu-id="7f960-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f960-115">See also</span></span>

- [<span data-ttu-id="7f960-116">加载项管理</span><span class="sxs-lookup"><span data-stu-id="7f960-116">Add-in administration</span></span>](add-in-administration.md)

