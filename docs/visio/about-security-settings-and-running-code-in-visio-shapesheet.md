---
title: 关于安全设置和运行 Visio (ShapeSheet) 中的代码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm1042370
localization_priority: Normal
ms.assetid: 506b3d81-9c93-aeff-f5b2-3354ffd3e075
description: 创建安全的应用程序是一个主要解决方案开发人员所面临的挑战。 用户、 管理员和开发人员都日益认识不知情的情况下运行的代码可对其计算机有害的潜在。 很多重要比以往帮助确保您的应用程序的完整性。
ms.openlocfilehash: 72b4a45faa46778b7a369cfe458ee4e0e9ea71bb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396552"
---
# <a name="about-security-settings-and-running-code-in-visio-shapesheet"></a><span data-ttu-id="162f2-105">关于安全设置和运行 Visio (ShapeSheet) 中的代码</span><span class="sxs-lookup"><span data-stu-id="162f2-105">About Security Settings and Running Code in Visio (ShapeSheet)</span></span>

 <span data-ttu-id="162f2-106">创建安全的应用程序是一个主要解决方案开发人员所面临的挑战。</span><span class="sxs-lookup"><span data-stu-id="162f2-106">Creating secure applications is one of the primary challenges facing solution developers.</span></span> <span data-ttu-id="162f2-107">用户、 管理员和开发人员都日益认识不知情的情况下运行的代码可对其计算机有害的潜在。</span><span class="sxs-lookup"><span data-stu-id="162f2-107">Users, administrators, and developers are increasingly aware of the potential of unknowingly running code that can be harmful to their computers.</span></span> <span data-ttu-id="162f2-108">很多重要比以往帮助确保您的应用程序的完整性。</span><span class="sxs-lookup"><span data-stu-id="162f2-108">It is more important than ever that you help to ensure the integrity of your applications.</span></span> 
  
<span data-ttu-id="162f2-109">Office 范围和在**信任中心**设置所有安全设置 （单击**文件**选项卡，单击**选项**，然后单击**信任中心**）。</span><span class="sxs-lookup"><span data-stu-id="162f2-109">All security settings are Office-wide and are set in the **Trust Center** (click the **File** tab, click **Options**, and then click **Trust Center**).</span></span> <span data-ttu-id="162f2-110">受影响的设置包括：</span><span class="sxs-lookup"><span data-stu-id="162f2-110">Affected settings include the following:</span></span>
  
- <span data-ttu-id="162f2-111">指定可靠发行商</span><span class="sxs-lookup"><span data-stu-id="162f2-111">Specifying trusted publishers</span></span>
    
- <span data-ttu-id="162f2-112">指定可靠位置</span><span class="sxs-lookup"><span data-stu-id="162f2-112">Specifying trusted locations</span></span>
    
- <span data-ttu-id="162f2-113">加载 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="162f2-113">Loading COM add-ins</span></span> 
    
- <span data-ttu-id="162f2-114">加载已发布和已发现路径的加载项</span><span class="sxs-lookup"><span data-stu-id="162f2-114">Loading published and path-discovered add-ons</span></span>
    
- <span data-ttu-id="162f2-115">加载 VBA 宏</span><span class="sxs-lookup"><span data-stu-id="162f2-115">Loading VBA macros</span></span>
    
<span data-ttu-id="162f2-116">在 Visio 以前的版本，在**安全**对话框和**选项**对话框的**工具**菜单的**安全**选项卡中进行设置。</span><span class="sxs-lookup"><span data-stu-id="162f2-116">In previous versions of Visio, settings were made in the **Security** dialog box and the **Security** tab of the **Options** dialog box (**Tools** menu).</span></span> <span data-ttu-id="162f2-117">Office Visio 2007 截止淘汰了这些对话框，并从 Microsoft Visio 2010，Visio 工具栏和菜单已替换为功能区。</span><span class="sxs-lookup"><span data-stu-id="162f2-117">As of Office Visio 2007, these dialog boxes have been eliminated, and as of Microsoft Visio 2010, Visio toolbars and menus have been replaced by the ribbon.</span></span> 
  
<span data-ttu-id="162f2-118">有关 Office**信任中心**中设置的详细信息，请参阅[Microsoft Office 解决方案开发人员安全备注](https://msdn.microsoft.com/en-us/library/aa433259.aspx)。</span><span class="sxs-lookup"><span data-stu-id="162f2-118">For more information about settings in the Office **Trust Center**, see [Security Notes for Microsoft Office Solution Developers](https://msdn.microsoft.com/en-us/library/aa433259.aspx).</span></span>
  
 <span data-ttu-id="162f2-119">有关代码进行数字签名以及可靠的来源和发行商的信息，搜索"代码签名"MSDN，Microsoft Developer Network 网站上。</span><span class="sxs-lookup"><span data-stu-id="162f2-119">For information about digitally signing code and trusted sources and publishers, search for "code signing" on MSDN, the Microsoft Developer Network website.</span></span> 
  
<span data-ttu-id="162f2-120">有关优秀安全设计行为和技术的详细信息，请在 MSDN 上搜索“security”（安全）。</span><span class="sxs-lookup"><span data-stu-id="162f2-120">For more information about good security design practices and technologies, search for "security" on MSDN.</span></span> 
  
## <a name="additional-visio-resources"></a><span data-ttu-id="162f2-121">其他 Visio 资源</span><span class="sxs-lookup"><span data-stu-id="162f2-121">Additional Visio resources</span></span>

- <span data-ttu-id="162f2-122">若要了解有关 Visio 加载项和 COM 加载项的详细信息，请参阅 MSDN 文章[概述的加载项和 COM 加载项在 Visio 2007 中](https://msdn.microsoft.com/library/bb851468.aspx)。</span><span class="sxs-lookup"><span data-stu-id="162f2-122">To learn more about Visio add-ons and COM add-ins, see the MSDN article, [Overview of Add-ons and COM Add-ins in Visio 2007](https://msdn.microsoft.com/library/bb851468.aspx).</span></span>
    
- <span data-ttu-id="162f2-123">若要了解有关 RUNADDON 函数和**AddonName**属性的详细信息，请参阅 MSDN 文章[RUNADDON 函数和 AddOnName 属性的 Visio 2002 中的更改](https://msdn.microsoft.com/library/aa140368%28office.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="162f2-123">To learn more about the RUNADDON function and the **AddonName** property, see the MSDN article [Changes in the RUNADDON Function and the AddOnName Property for Visio 2002](https://msdn.microsoft.com/library/aa140368%28office.10%29.aspx).</span></span>
    

