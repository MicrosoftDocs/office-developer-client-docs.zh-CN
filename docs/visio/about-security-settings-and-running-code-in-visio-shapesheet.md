---
title: 关于 Visio 中的安全设置和运行代码（ShapeSheet）
manager: lindalu
ms.date: 12/03/2019
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm1042370
localization_priority: Normal
ms.assetid: 506b3d81-9c93-aeff-f5b2-3354ffd3e075
description: 解决方案开发人员面对的主要挑战之一便是创建安全的应用程序。 用户、管理员和开发人员越来越多地意识到在不知情的情况下可能会对其计算机造成危害的代码。 帮助您确保应用程序的完整性正变得前所未有的重要。
ms.openlocfilehash: 3ad2aef9096ad2ad344b2d6fb22ed610756916bb
ms.sourcegitcommit: 37080eb0087261320e24e6f067e5f434a812b2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819264"
---
# <a name="about-security-settings-and-running-code-in-visio-shapesheet"></a>关于 Visio 中的安全设置和运行代码（ShapeSheet）

 解决方案开发人员面对的主要挑战之一便是创建安全的应用程序。 用户、管理员和开发人员越来越多地意识到在不知情的情况下可能会对其计算机造成危害的代码。 帮助您确保应用程序的完整性正变得前所未有的重要。 
  
所有安全设置都是 Office 范围的，并在**信任中心**（单击 "**文件**" 选项卡，单击 "**选项**"，然后单击 "**信任中心**"）进行设置。 受影响的设置包括以下各项：
  
- 指定可靠发行商
    
- 指定可靠位置
    
- 加载 COM 加载项 
    
- 加载已发布和已发现路径的加载项
    
- 加载 VBA 宏
    
在以前的 Visio 版本中，在 **“安全性”** 对话框和 **“选项”** 对话框（**“工具”** 菜单）的 **“安全性”** 选项卡中进行设置。 从 Office Visio 2007，这些对话框已被消除，而在 Microsoft Visio 2010 中，Visio 工具栏和菜单已由功能区取代。 
  
有关 Office**信任中心**中的设置的详细信息，请参阅[Microsoft Office 解决方案开发人员的安全说明](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa433259(v=office.12))。
  
 有关数字签名代码和受信任源和发布者的信息，请在 MSDN （Microsoft Developer Network 网站）上搜索 "代码签名"。 
  
有关优秀安全设计行为和技术的详细信息，请在 MSDN 上搜索“security”（安全）。 
  
## <a name="additional-visio-resources"></a>其他 Visio 资源

- 若要了解有关 Visio 加载项和 COM 加载项的详细信息，请参阅 MSDN 文章： [visio 2007 中的加载项和 COM 加载项概述](https://docs.microsoft.com/previous-versions/office/developer/office-2007/bb851468(v=office.12))。
    
- 若要了解有关 RUNADDON 函数和**AddonName**属性的详细信息，请参阅 MSDN 文章[在 RUNADDON 函数中的更改和 Visio 2002 的 AddonName 属性](https://docs.microsoft.com/previous-versions/office/developer/office-xp/aa140368(v=office.10))。
    

