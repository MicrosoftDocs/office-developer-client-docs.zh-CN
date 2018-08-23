---
title: 安装 MAPI 子系统
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 29fb4c44-1a59-457e-813b-a982bd72891c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: adb4d09ccce95683ac46e7b271fafa328b1a9f97
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575348"
---
# <a name="installing-the-mapi-subsystem"></a><span data-ttu-id="cdffc-103">安装 MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="cdffc-103">Installing the MAPI Subsystem</span></span>

  
  
<span data-ttu-id="cdffc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cdffc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cdffc-105">受支持的版本的 Windows 中安装的 MAPI 存根库 Mapi32.dll，_\<驱动器\>_ \Windows\System32 文件夹。</span><span class="sxs-lookup"><span data-stu-id="cdffc-105">Supported versions of Windows install the MAPI stub library, Mapi32.dll, in the  _\<drive\>_ \Windows\System32 folder.</span></span> 
  
<span data-ttu-id="cdffc-106">支持的 Windows 版本如下所示：</span><span class="sxs-lookup"><span data-stu-id="cdffc-106">The supported versions of Windows are as follows:</span></span>
  
- <span data-ttu-id="cdffc-107">Windows 7。</span><span class="sxs-lookup"><span data-stu-id="cdffc-107">Windows 7.</span></span>
    
- <span data-ttu-id="cdffc-108">Windows Vista。</span><span class="sxs-lookup"><span data-stu-id="cdffc-108">Windows Vista.</span></span>
    
- <span data-ttu-id="cdffc-109">Windows Server 2008。</span><span class="sxs-lookup"><span data-stu-id="cdffc-109">Windows Server 2008.</span></span>
    
- <span data-ttu-id="cdffc-110">Windows Server 2003。</span><span class="sxs-lookup"><span data-stu-id="cdffc-110">Windows Server 2003.</span></span>
    
- <span data-ttu-id="cdffc-111">Windows XP。</span><span class="sxs-lookup"><span data-stu-id="cdffc-111">Windows XP.</span></span>
    
<span data-ttu-id="cdffc-112">若要正确安装 MAPI 子系统，安装包含基于 MAPI 的子系统，如 Microsoft Outlook 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cdffc-112">To correctly install the MAPI subsystem, install an application that contains a MAPI-based subsystem, such as Microsoft Outlook.</span></span>
  
<span data-ttu-id="cdffc-113">您可以在系统注册表中找到有关计算机的 MAPI 子系统安装的信息。</span><span class="sxs-lookup"><span data-stu-id="cdffc-113">You can find information about a computer's MAPI subsystem installation in the system registry.</span></span> <span data-ttu-id="cdffc-114">注册表项中的所有值都的字符串。</span><span class="sxs-lookup"><span data-stu-id="cdffc-114">All values in the registry entries are character strings.</span></span> 
  
<span data-ttu-id="cdffc-115">消息服务安装程序负责在以下系统注册表项中创建了安装信息：</span><span class="sxs-lookup"><span data-stu-id="cdffc-115">Message service installation programs are responsible for creating the installation information in the following system registry key:</span></span> 
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Messaging Subsystem`
  
<span data-ttu-id="cdffc-116">消息服务必须添加到系统注册表项。</span><span class="sxs-lookup"><span data-stu-id="cdffc-116">Message services must add entries to the system registry.</span></span> 
  
<span data-ttu-id="cdffc-117">下表总结了客户端如何检索 MAPI 子系统在其计算机上的版本信息。</span><span class="sxs-lookup"><span data-stu-id="cdffc-117">The following table summarizes how clients retrieve version information for the MAPI subsystem on their computer.</span></span>
  
|<span data-ttu-id="cdffc-118">**若要检查**</span><span class="sxs-lookup"><span data-stu-id="cdffc-118">**To check**</span></span>|<span data-ttu-id="cdffc-119">**Registry**</span><span class="sxs-lookup"><span data-stu-id="cdffc-119">**Registry**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cdffc-120">MAPI 的可用性</span><span class="sxs-lookup"><span data-stu-id="cdffc-120">Availability of MAPI</span></span>  <br/> |<span data-ttu-id="cdffc-121">查找`MAPIX=1`。</span><span class="sxs-lookup"><span data-stu-id="cdffc-121">Look for  `MAPIX=1`.</span></span>  <br/> |
|<span data-ttu-id="cdffc-122">可用版本的 MAPI</span><span class="sxs-lookup"><span data-stu-id="cdffc-122">Available version of MAPI</span></span>  <br/> |<span data-ttu-id="cdffc-123">查找窗体" _x.x.x_"MAPIXVER 字符串。</span><span class="sxs-lookup"><span data-stu-id="cdffc-123">Look for a MAPIXVER string of the form " _x.x.x_".</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cdffc-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdffc-124">See also</span></span>



[<span data-ttu-id="cdffc-125">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="cdffc-125">MAPI Programming Overview</span></span>](mapi-programming-overview.md)

