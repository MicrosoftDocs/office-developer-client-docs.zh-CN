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
# <a name="about-security-settings-and-running-code-in-visio-shapesheet"></a>关于 ShapeSheet 设置中的安全Visio (代码) 

 解决方案开发人员面对的主要挑战之一便是创建安全的应用程序。 用户、管理员和开发人员越来越了解在无意中运行可能危害其计算机的代码的可能性。 帮助您确保应用程序的完整性正变得前所未有的重要。 
  
所有安全设置都是Office范围的，在信任中心设置 ("文件"选项卡，单击"选项"，然后单击"信任中心") 。   受影响的设置包括：
  
- 指定可靠发行商
    
- 指定可靠位置
    
- 加载 COM 加载项 
    
- 加载已发布和已发现路径的加载项
    
- 加载 VBA 宏
    
在以前的 Visio 版本中，在 **“安全性”** 对话框和 **“选项”** 对话框（**“工具”** 菜单）的 **“安全性”** 选项卡中进行设置。 自 2007 Office Visio起，已取消这些对话框，自 Microsoft Visio 2010 起，Visio工具栏和菜单已替换为功能区。 
  
有关信任中心中设置 **Office，** 请参阅解决方案开发人员Microsoft Office [安全说明](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa433259(v=office.12))。
  
 有关对代码进行数字签名以及受信任的源和发布者的信息，请搜索 MSDN（即网站）上的"Microsoft 开发人员网络签名"。 
  
有关优秀安全设计行为和技术的详细信息，请在 MSDN 上搜索“security”（安全）。 
  
## <a name="additional-visio-resources"></a>其他 Visio 资源

- 若要详细了解Visio加载项和 COM 加载项，请参阅 MSDN 文章 Overview [of Add-ons and COM Add-ins in Visio 2007。](https://docs.microsoft.com/previous-versions/office/developer/office-2007/bb851468(v=office.12))
    
- 若要详细了解 RUNADDON 函数和 **AddonName** 属性，请参阅 MSDN 文章 [Changes in the RUNADDON Function and the AddOnName Property for Visio 2002](https://docs.microsoft.com/previous-versions/office/developer/office-xp/aa140368(v=office.10))。
    

