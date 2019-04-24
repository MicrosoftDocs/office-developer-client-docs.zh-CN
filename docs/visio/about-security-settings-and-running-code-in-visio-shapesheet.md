---
title: 关于 Visio 中的安全设置和运行代码 (ShapeSheet)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm1042370
localization_priority: Normal
ms.assetid: 506b3d81-9c93-aeff-f5b2-3354ffd3e075
description: 解决方案开发人员面对的主要挑战之一便是创建安全的应用程序。 用户、管理员和开发人员越来越多地意识到在不知情的情况下可能会对其计算机造成危害的代码。 帮助您确保应用程序的完整性正变得前所未有的重要。
ms.openlocfilehash: 72b4a45faa46778b7a369cfe458ee4e0e9ea71bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345022"
---
# <a name="about-security-settings-and-running-code-in-visio-shapesheet"></a>关于 Visio 中的安全设置和运行代码 (ShapeSheet)

 解决方案开发人员面对的主要挑战之一便是创建安全的应用程序。 用户、管理员和开发人员越来越多地意识到在不知情的情况下可能会对其计算机造成危害的代码。 帮助您确保应用程序的完整性正变得前所未有的重要。 
  
所有安全设置都是 Office 范围的, 并在**信任中心**(单击 "**文件**" 选项卡, 单击 "**选项**", 然后单击 "**信任中心**") 进行设置。 受影响的设置包括以下各项:
  
- 指定可靠发行商
    
- 指定可靠位置
    
- 加载 COM 加载项 
    
- 加载已发布和已发现路径的加载项
    
- 加载 VBA 宏
    
在以前的 Visio 版本中，在 **“安全性”** 对话框和 **“选项”** 对话框（**“工具”** 菜单）的 **“安全性”** 选项卡中进行设置。 从 Office visio 2007, 这些对话框已被消除, 而在 Microsoft Visio 2010 中, visio 工具栏和菜单已由功能区取代。 
  
有关 Office**信任中心**中的设置的详细信息, 请参阅[Microsoft Office 解决方案开发人员的安全说明](https://msdn.microsoft.com/en-us/library/aa433259.aspx)。
  
 有关数字签名代码和受信任源和发布者的信息, 请在 MSDN (Microsoft Developer Network 网站) 上搜索 "代码签名"。 
  
有关优秀安全设计行为和技术的详细信息，请在 MSDN 上搜索“security”（安全）。 
  
## <a name="additional-visio-resources"></a>其他 Visio 资源

- 若要了解有关 visio 加载项和 com 加载项的详细信息, 请参阅 MSDN 文章: [visio 2007 中的加载项和 COM 加载项概述](https://msdn.microsoft.com/library/bb851468.aspx)。
    
- 若要了解有关 RUNADDON 函数和**AddonName**属性的详细信息, 请参阅 MSDN 文章[在 RUNADDON 函数中的更改和 Visio 2002 的 AddonName 属性](https://msdn.microsoft.com/library/aa140368%28office.10%29.aspx)。
    

