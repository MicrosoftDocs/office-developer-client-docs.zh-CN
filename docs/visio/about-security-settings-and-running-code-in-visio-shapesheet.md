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
ms.openlocfilehash: e114fef650f31a6e0adf368d339f71e3a32113f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779599"
---
# <a name="about-security-settings-and-running-code-in-visio-shapesheet"></a>关于安全设置和运行 Visio (ShapeSheet) 中的代码

 创建安全的应用程序是一个主要解决方案开发人员所面临的挑战。 用户、 管理员和开发人员都日益认识不知情的情况下运行的代码可对其计算机有害的潜在。 很多重要比以往帮助确保您的应用程序的完整性。 
  
Office 范围和在**信任中心**设置所有安全设置 （单击**文件**选项卡，单击**选项**，然后单击**信任中心**）。 受影响的设置包括：
  
- 指定可靠发行商
    
- 指定可靠位置
    
- 加载 COM 加载项 
    
- 加载已发布和已发现路径的加载项
    
- 加载 VBA 宏
    
在 Visio 以前的版本，在**安全**对话框和**选项**对话框的**工具**菜单的**安全**选项卡中进行设置。 Office Visio 2007 截止淘汰了这些对话框，并从 Microsoft Visio 2010，Visio 工具栏和菜单已替换为功能区。 
  
有关 Office**信任中心**中设置的详细信息，请参阅[Microsoft Office 解决方案开发人员安全备注](http://msdn2.microsoft.com/en-us/library/aa433259.aspx)。
  
 有关对代码进行数字签名以及可靠来源和发行商的信息，请在 Microsoft Developer Network 网站 (MSDN) 上搜索“code signing”（代码签名）。 
  
有关优秀安全设计行为和技术的详细信息，请在 MSDN 上搜索“security”（安全）。 
  
## <a name="additional-visio-resources"></a>其他 Visio 资源

- 若要了解有关 Visio 加载项和 COM 加载项的详细信息，请参阅 MSDN 文章[概述的加载项和 COM 加载项在 Visio 2007 中](http://msdn.microsoft.com/en-us/library/bb851468.aspx)。
    
- 若要了解有关 RUNADDON 函数和**AddonName**属性的详细信息，请参阅 MSDN 文章[RUNADDON 函数和 AddOnName 属性的 Visio 2002 中的更改](http://msdn.microsoft.com/en-us/library/aa140368%28office.10%29.aspx)。
    

