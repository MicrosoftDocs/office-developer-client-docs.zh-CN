---
title: 使用 Visual Studio Office 开发人员工具提供的受信任应用程序对象
TOCTitle: Using a trusted application object provided by Office Developer Tools for Visual Studio
ms:assetid: 3778122f-f60e-48e7-8e72-f3aef168bae2
ms:mtpsurl: https://msdn.microsoft.com/library/Bb622502(v=office.15)
ms:contentKeyID: 55119787
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f86ad294e894b4faea10d033a069638221f1bd78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285170"
---
# <a name="using-a-trusted-application-object-provided-by-office-developer-tools-for-visual-studio"></a>使用 Visual Studio Office 开发人员工具提供的受信任应用程序对象

若要使用 Visual Studio Office 开发人员工具开发托管加载项，请始终使用 Visual Studio 提供的 [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象。 

除非您要自动创建 Outlook 的新实例，否则请勿使用 New 或 new 关键字创建 Outlook 的新实例，因为 **Application** 对象的此实例不受 Outlook 对象模型保护信任。 

如果您的加载项使用 **Application** 对象的不受信任实例，则默认情况下，该加载项将根据客户端正在运行的 Outlook 的版本对该对象模型的多个成员调用 Outlook 的对象模型保护。 

若要详细了解 Object Model Guard 的行为，请参阅 [Outlook 2007 中的代码安全性更改](https://msdn.microsoft.com/library/bb226709\(v=office.15\))。 请注意，虽然“Outlook 2007 中的代码安全性更改”一文引用了默认受信任的 COM 加载项，但此设计适用于自 Outlook 2007 后发布的 Outlook 版本，同样信任也适用于托管加载项。 无论加载项是否为托管的加载项，该信任都将基于加载项使用受信任的 **Application** 对象这一假设。

