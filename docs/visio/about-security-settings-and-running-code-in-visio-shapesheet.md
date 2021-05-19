---
title: '关于 ShapeSheet 设置中的安全Visio (代码) '
manager: lindalu
ms.date: 12/03/2019
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm1042370
localization_priority: Normal
ms.assetid: 506b3d81-9c93-aeff-f5b2-3354ffd3e075
description: 解决方案开发人员面对的主要挑战之一便是创建安全的应用程序。 用户、管理员和开发人员越来越了解在无意中运行可能危害其计算机的代码的可能性。 帮助您确保应用程序的完整性正变得前所未有的重要。
ms.openlocfilehash: 3ad2aef9096ad2ad344b2d6fb22ed610756916bb
ms.sourcegitcommit: 37080eb0087261320e24e6f067e5f434a812b2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819264"
---
# <a name="about-security-settings-and-running-code-in-visio-shapesheet"></a><span data-ttu-id="d4107-105">关于 ShapeSheet 设置中的安全Visio (代码) </span><span class="sxs-lookup"><span data-stu-id="d4107-105">About Security Settings and Running Code in Visio (ShapeSheet)</span></span>

 <span data-ttu-id="d4107-106">解决方案开发人员面对的主要挑战之一便是创建安全的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4107-106">Creating secure applications is one of the primary challenges facing solution developers.</span></span> <span data-ttu-id="d4107-107">用户、管理员和开发人员越来越了解在无意中运行可能危害其计算机的代码的可能性。</span><span class="sxs-lookup"><span data-stu-id="d4107-107">Users, administrators, and developers are increasingly aware of the potential of unknowingly running code that can be harmful to their computers.</span></span> <span data-ttu-id="d4107-108">帮助您确保应用程序的完整性正变得前所未有的重要。</span><span class="sxs-lookup"><span data-stu-id="d4107-108">It is more important than ever that you help to ensure the integrity of your applications.</span></span> 
  
<span data-ttu-id="d4107-109">所有安全设置都是Office范围的，在信任中心设置 ("文件"选项卡，单击"选项"，然后单击"信任中心") 。  </span><span class="sxs-lookup"><span data-stu-id="d4107-109">All security settings are Office-wide and are set in the **Trust Center** (click the **File** tab, click **Options**, and then click **Trust Center**).</span></span> <span data-ttu-id="d4107-110">受影响的设置包括：</span><span class="sxs-lookup"><span data-stu-id="d4107-110">Affected settings include the following:</span></span>
  
- <span data-ttu-id="d4107-111">指定可靠发行商</span><span class="sxs-lookup"><span data-stu-id="d4107-111">Specifying trusted publishers</span></span>
    
- <span data-ttu-id="d4107-112">指定可靠位置</span><span class="sxs-lookup"><span data-stu-id="d4107-112">Specifying trusted locations</span></span>
    
- <span data-ttu-id="d4107-113">加载 COM 加载项</span><span class="sxs-lookup"><span data-stu-id="d4107-113">Loading COM add-ins</span></span> 
    
- <span data-ttu-id="d4107-114">加载已发布和已发现路径的加载项</span><span class="sxs-lookup"><span data-stu-id="d4107-114">Loading published and path-discovered add-ons</span></span>
    
- <span data-ttu-id="d4107-115">加载 VBA 宏</span><span class="sxs-lookup"><span data-stu-id="d4107-115">Loading VBA macros</span></span>
    
<span data-ttu-id="d4107-116">在以前的 Visio 版本中，在 **“安全性”** 对话框和 **“选项”** 对话框（**“工具”** 菜单）的 **“安全性”** 选项卡中进行设置。</span><span class="sxs-lookup"><span data-stu-id="d4107-116">In previous versions of Visio, settings were made in the **Security** dialog box and the **Security** tab of the **Options** dialog box (**Tools** menu).</span></span> <span data-ttu-id="d4107-117">自 2007 Office Visio起，已取消这些对话框，自 Microsoft Visio 2010 起，Visio工具栏和菜单已替换为功能区。</span><span class="sxs-lookup"><span data-stu-id="d4107-117">As of Office Visio 2007, these dialog boxes have been eliminated, and as of Microsoft Visio 2010, Visio toolbars and menus have been replaced by the ribbon.</span></span> 
  
<span data-ttu-id="d4107-118">有关信任中心中设置 **Office，** 请参阅解决方案开发人员Microsoft Office [安全说明](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa433259(v=office.12))。</span><span class="sxs-lookup"><span data-stu-id="d4107-118">For more information about settings in the Office **Trust Center**, see [Security Notes for Microsoft Office Solution Developers](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa433259(v=office.12)).</span></span>
  
 <span data-ttu-id="d4107-119">有关对代码进行数字签名以及受信任的源和发布者的信息，请搜索 MSDN（即网站）上的"Microsoft 开发人员网络签名"。</span><span class="sxs-lookup"><span data-stu-id="d4107-119">For information about digitally signing code and trusted sources and publishers, search for "code signing" on MSDN, the Microsoft Developer Network website.</span></span> 
  
<span data-ttu-id="d4107-120">有关优秀安全设计行为和技术的详细信息，请在 MSDN 上搜索“security”（安全）。</span><span class="sxs-lookup"><span data-stu-id="d4107-120">For more information about good security design practices and technologies, search for "security" on MSDN.</span></span> 
  
## <a name="additional-visio-resources"></a><span data-ttu-id="d4107-121">其他 Visio 资源</span><span class="sxs-lookup"><span data-stu-id="d4107-121">Additional Visio resources</span></span>

- <span data-ttu-id="d4107-122">若要详细了解Visio加载项和 COM 加载项，请参阅 MSDN 文章 Overview [of Add-ons and COM Add-ins in Visio 2007。](https://docs.microsoft.com/previous-versions/office/developer/office-2007/bb851468(v=office.12))</span><span class="sxs-lookup"><span data-stu-id="d4107-122">To learn more about Visio add-ons and COM add-ins, see the MSDN article, [Overview of Add-ons and COM Add-ins in Visio 2007](https://docs.microsoft.com/previous-versions/office/developer/office-2007/bb851468(v=office.12)).</span></span>
    
- <span data-ttu-id="d4107-123">若要详细了解 RUNADDON 函数和 **AddonName** 属性，请参阅 MSDN 文章 [Changes in the RUNADDON Function and the AddOnName Property for Visio 2002](https://docs.microsoft.com/previous-versions/office/developer/office-xp/aa140368(v=office.10))。</span><span class="sxs-lookup"><span data-stu-id="d4107-123">To learn more about the RUNADDON function and the **AddonName** property, see the MSDN article [Changes in the RUNADDON Function and the AddOnName Property for Visio 2002](https://docs.microsoft.com/previous-versions/office/developer/office-xp/aa140368(v=office.10)).</span></span>
    

