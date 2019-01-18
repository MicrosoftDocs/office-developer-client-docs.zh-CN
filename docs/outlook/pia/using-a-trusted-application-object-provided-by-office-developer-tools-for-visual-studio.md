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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703011"
---
# <a name="using-a-trusted-application-object-provided-by-office-developer-tools-for-visual-studio"></a><span data-ttu-id="df782-102">使用 Visual Studio Office 开发人员工具提供的受信任应用程序对象</span><span class="sxs-lookup"><span data-stu-id="df782-102">Using a trusted Application object provided by Office Developer Tools for Visual Studio</span></span>

<span data-ttu-id="df782-103">若要使用 Visual Studio Office 开发人员工具开发托管加载项，请始终使用 Visual Studio 提供的 [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="df782-103">If you are developing a managed add-in by using Office Developer Tools for Visual Studio, always use the [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) object that is provided by Visual Studio.</span></span> 

<span data-ttu-id="df782-104">除非您要自动创建 Outlook 的新实例，否则请勿使用 New 或 new 关键字创建 Outlook 的新实例，因为 **Application** 对象的此实例不受 Outlook 对象模型保护信任。</span><span class="sxs-lookup"><span data-stu-id="df782-104">Unless you intend to automate a new instance of Outlook, do not use the New or new keyword to create a new instance of Outlook, as this instance of the **Application** object is not trusted from the perspective of the Outlook Object Model Guard.</span></span> 

<span data-ttu-id="df782-105">如果您的加载项使用 **Application** 对象的不受信任实例，则默认情况下，该加载项将根据客户端正在运行的 Outlook 的版本对该对象模型的多个成员调用 Outlook 的对象模型保护。</span><span class="sxs-lookup"><span data-stu-id="df782-105">If your add-in uses an untrusted instance of the **Application** object, depending on the version of Outlook that the client is running, the add-in by default will invoke Outlook's Object Model Guard on a number of members of the object model.</span></span> 

<span data-ttu-id="df782-106">若要详细了解 Object Model Guard 的行为，请参阅 [Outlook 2007 中的代码安全性更改](https://msdn.microsoft.com/library/bb226709\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="df782-106">For more information about the behavior of the Object Model Guard, see [Code Security Changes in Outlook 2007](https://msdn.microsoft.com/library/bb226709\(v=office.15\)).</span></span> <span data-ttu-id="df782-107">请注意，虽然“Outlook 2007 中的代码安全性更改”一文引用了默认受信任的 COM 加载项，但此设计适用于自 Outlook 2007 后发布的 Outlook 版本，同样信任也适用于托管加载项。</span><span class="sxs-lookup"><span data-stu-id="df782-107">Note that even though the "Code Security Changes in Outlook 2007" article refers to COM add-ins that are trusted by default, this design applies to versions of Outlook since Outlook 2007, and the trust applies to managed add-ins the same way.</span></span> <span data-ttu-id="df782-108">无论加载项是否为托管的加载项，该信任都将基于加载项使用受信任的 **Application** 对象这一假设。</span><span class="sxs-lookup"><span data-stu-id="df782-108">Regardless of whether the add-in is managed or not, the trust is based on the assumption that the add-in uses a trusted **Application** object.</span></span>

