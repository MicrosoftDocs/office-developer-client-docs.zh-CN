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
ms.openlocfilehash: c2e135fc031dd3faf5a4e08c50147dfcf7787b5e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775939"
---
# <a name="installing-the-mapi-subsystem"></a><span data-ttu-id="9fddb-103">安装 MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="9fddb-103">Installing the MAPI Subsystem</span></span>

  
  
<span data-ttu-id="9fddb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9fddb-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9fddb-105">受支持的版本的 Windows 中安装的 MAPI 存根库 Mapi32.dll，_\<驱动器\>_ \Windows\System32 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9fddb-105">Supported versions of Windows install the MAPI stub library, Mapi32.dll, in the  _\<drive\>_ \Windows\System32 folder.</span></span> 
  
<span data-ttu-id="9fddb-106">支持的 Windows 版本如下所示：</span><span class="sxs-lookup"><span data-stu-id="9fddb-106">The supported versions of Windows are as follows:</span></span>
  
- <span data-ttu-id="9fddb-107">Windows 7。</span><span class="sxs-lookup"><span data-stu-id="9fddb-107">Windows 7.</span></span>
    
- <span data-ttu-id="9fddb-108">Windows Vista。</span><span class="sxs-lookup"><span data-stu-id="9fddb-108">Windows Vista.</span></span>
    
- <span data-ttu-id="9fddb-109">Windows Server 2008。</span><span class="sxs-lookup"><span data-stu-id="9fddb-109">Windows Server 2008.</span></span>
    
- <span data-ttu-id="9fddb-110">Windows Server 2003。</span><span class="sxs-lookup"><span data-stu-id="9fddb-110">Windows Server 2003.</span></span>
    
- <span data-ttu-id="9fddb-111">Windows XP。</span><span class="sxs-lookup"><span data-stu-id="9fddb-111">Windows XP.</span></span>
    
<span data-ttu-id="9fddb-112">若要正确安装 MAPI 子系统，安装包含基于 MAPI 的子系统，如 Microsoft Outlook 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9fddb-112">To correctly install the MAPI subsystem, install an application that contains a MAPI-based subsystem, such as Microsoft Outlook.</span></span>
  
<span data-ttu-id="9fddb-113">您可以在系统注册表中找到有关计算机的 MAPI 子系统安装的信息。</span><span class="sxs-lookup"><span data-stu-id="9fddb-113">You can find information about a computer's MAPI subsystem installation in the system registry.</span></span> <span data-ttu-id="9fddb-114">注册表项中的所有值都的字符串。</span><span class="sxs-lookup"><span data-stu-id="9fddb-114">All values in the registry entries are character strings.</span></span> 
  
<span data-ttu-id="9fddb-115">消息服务安装程序负责在以下系统注册表项中创建了安装信息：</span><span class="sxs-lookup"><span data-stu-id="9fddb-115">Message service installation programs are responsible for creating the installation information in the following system registry key:</span></span> 
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Messaging Subsystem`
  
<span data-ttu-id="9fddb-116">消息服务必须添加到系统注册表项。</span><span class="sxs-lookup"><span data-stu-id="9fddb-116">Message services must add entries to the system registry.</span></span> 
  
<span data-ttu-id="9fddb-117">下表总结了客户端如何检索 MAPI 子系统在其计算机上的版本信息。</span><span class="sxs-lookup"><span data-stu-id="9fddb-117">The following table summarizes how clients retrieve version information for the MAPI subsystem on their computer.</span></span>
  
|<span data-ttu-id="9fddb-118">**若要检查**</span><span class="sxs-lookup"><span data-stu-id="9fddb-118">**To check**</span></span>|<span data-ttu-id="9fddb-119">**Registry**</span><span class="sxs-lookup"><span data-stu-id="9fddb-119">**Registry**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9fddb-120">MAPI 的可用性</span><span class="sxs-lookup"><span data-stu-id="9fddb-120">Availability of MAPI</span></span>  <br/> |<span data-ttu-id="9fddb-121">查找`MAPIX=1`。</span><span class="sxs-lookup"><span data-stu-id="9fddb-121">Look for  `MAPIX=1`.</span></span>  <br/> |
|<span data-ttu-id="9fddb-122">可用版本的 MAPI</span><span class="sxs-lookup"><span data-stu-id="9fddb-122">Available version of MAPI</span></span>  <br/> |<span data-ttu-id="9fddb-123">查找窗体" _x.x.x_"MAPIXVER 字符串。</span><span class="sxs-lookup"><span data-stu-id="9fddb-123">Look for a MAPIXVER string of the form " _x.x.x_".</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9fddb-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fddb-124">See also</span></span>



[<span data-ttu-id="9fddb-125">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="9fddb-125">MAPI Programming Overview</span></span>](mapi-programming-overview.md)

