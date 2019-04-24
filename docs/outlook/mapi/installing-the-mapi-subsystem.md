---
title: 安装 MAPI 子系统
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
api_type:
- COM
ms.assetid: 29fb4c44-1a59-457e-813b-a982bd72891c
description: 上次修改时间：2015 年 3 月 9 日
localization_priority: Priority
ms.openlocfilehash: 112a683f5967f8740c2d21285eb4ebbc0f455c48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309637"
---
# <a name="installing-the-mapi-subsystem"></a><span data-ttu-id="0c7d1-103">安装 MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="0c7d1-103">Installing the MAPI Subsystem</span></span>

  
  
<span data-ttu-id="0c7d1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c7d1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c7d1-105">受支持的 Windows 版本将 MAPI 存根库 Mapi32.dll 安装在 _\<drive\>_ \Windows\System32 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-105">Supported versions of Windows install the MAPI stub library, Mapi32.dll, in the  _\<drive\>_ \Windows\System32 folder.</span></span> 
  
<span data-ttu-id="0c7d1-106">受支持的 Windows 版本如下所示：</span><span class="sxs-lookup"><span data-stu-id="0c7d1-106">The supported versions of Windows are as follows:</span></span>
  
- <span data-ttu-id="0c7d1-107">Windows 7。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-107">Windows 7.</span></span>
    
- <span data-ttu-id="0c7d1-108">Windows Vista。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-108">Windows Vista.</span></span>
    
- <span data-ttu-id="0c7d1-109">Windows Server 2008。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-109">Windows Server 2008.</span></span>
    
- <span data-ttu-id="0c7d1-110">Windows Server 2003。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-110">Windows Server 2003.</span></span>
    
- <span data-ttu-id="0c7d1-111">Windows XP。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-111">Windows XP.</span></span>
    
<span data-ttu-id="0c7d1-112">若要正确安装 MAPI 系统，请安装包含基于 MAPI 子系统的应用程序，如 Microsoft Outlook。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-112">To correctly install the MAPI subsystem, install an application that contains a MAPI-based subsystem, such as Microsoft Outlook.</span></span>
  
<span data-ttu-id="0c7d1-113">可以在系统注册表中找到与计算机的 MAPI 子系统相关的信息。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-113">You can find information about a computer's MAPI subsystem installation in the system registry.</span></span> <span data-ttu-id="0c7d1-114">注册表项中的所有值均为字符字符串。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-114">All values in the registry entries are character strings.</span></span> 
  
<span data-ttu-id="0c7d1-115">邮件服务安装程序负责在以下系统注册表项中创建安装信息：</span><span class="sxs-lookup"><span data-stu-id="0c7d1-115">Message service installation programs are responsible for creating the installation information in the following system registry key:</span></span> 
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Messaging Subsystem`
  
<span data-ttu-id="0c7d1-116">邮件服务必须向系统注册表中添加注册表项。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-116">Message services must add entries to the system registry.</span></span> 
  
<span data-ttu-id="0c7d1-117">下表简要介绍了客户端如何检索其计算机上的 MAPI 子系统的版本信息。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-117">The following table summarizes how clients retrieve version information for the MAPI subsystem on their computer.</span></span>
  
|<span data-ttu-id="0c7d1-118">**检查**</span><span class="sxs-lookup"><span data-stu-id="0c7d1-118">**To check**</span></span>|<span data-ttu-id="0c7d1-119">**注册表**</span><span class="sxs-lookup"><span data-stu-id="0c7d1-119">**Registry**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0c7d1-120">MAPI 可用性</span><span class="sxs-lookup"><span data-stu-id="0c7d1-120">Availability of MAPI</span></span>  <br/> |<span data-ttu-id="0c7d1-121">查找 `MAPIX=1`。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-121">Look for  `MAPIX=1`.</span></span>  <br/> |
|<span data-ttu-id="0c7d1-122">可用的 MAPI 版本</span><span class="sxs-lookup"><span data-stu-id="0c7d1-122">Available version of MAPI</span></span>  <br/> |<span data-ttu-id="0c7d1-123">查找“_x.x.x_”形式的 MAPIXVER 字符串。</span><span class="sxs-lookup"><span data-stu-id="0c7d1-123">Look for a MAPIXVER string of the form " _x.x.x_".</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0c7d1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c7d1-124">See also</span></span>



[<span data-ttu-id="0c7d1-125">MAPI 编程概述</span><span class="sxs-lookup"><span data-stu-id="0c7d1-125">MAPI Programming Overview</span></span>](mapi-programming-overview.md)

