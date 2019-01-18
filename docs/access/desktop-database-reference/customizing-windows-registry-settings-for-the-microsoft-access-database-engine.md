---
title: 自定义 Microsoft Access 数据库引擎的 Windows 注册表设置
TOCTitle: Customizing Windows registry settings for the Microsoft Access database engine
ms:assetid: ca7e958a-ea26-d67d-45b9-10aeb1eac96b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834346(v=office.15)
ms:contentKeyID: 48547690
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- acmain11.chm1032168
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7cbe8ad56e01249563f7b06c9018d923a96246e9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707358"
---
# <a name="customizing-windows-registry-settings-for-the-microsoft-access-database-engine"></a><span data-ttu-id="7e4b7-102">自定义 Microsoft Access 数据库引擎的 Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7e4b7-102">Customizing Windows registry settings for the Microsoft Access database engine</span></span>

<span data-ttu-id="7e4b7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7e4b7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7e4b7-104">如果您的应用程序不能与 Microsoft Access 数据库引擎的默认功能正常工作，您可能需要更改设置以满足您需求的 Microsoft Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="7e4b7-104">If your application cannot work correctly with the default functionality of the Microsoft Access database engine, you may have to change the settings in the Microsoft Windows Registry to suit your needs.</span></span> <span data-ttu-id="7e4b7-105">Windows 注册表也可用于调整可安装的 ISAM 和 ODBC 驱动程序的操作。</span><span class="sxs-lookup"><span data-stu-id="7e4b7-105">The Windows Registry can also be used to tune the operation of the installable ISAM and ODBC driver.</span></span>

<span data-ttu-id="7e4b7-106">自定义 Windows 注册表设置有以下四种不同的方式：</span><span class="sxs-lookup"><span data-stu-id="7e4b7-106">You can customize the settings in the Windows Registry in four different ways:</span></span>

- [<span data-ttu-id="7e4b7-107">使用 Regedit.exe 覆盖默认设置</span><span class="sxs-lookup"><span data-stu-id="7e4b7-107">Using Regedit.exe to overwrite the default settings</span></span>](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/using-regedit-exe-to-overwrite-the-default-settings)
- [<span data-ttu-id="7e4b7-108">若要管理设置的应用程序的注册表树中创建一个分区</span><span class="sxs-lookup"><span data-stu-id="7e4b7-108">Creating a portion in your application's registry tree to manage the settings</span></span>](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/creating-a-portion-in-your-application-s-registry-tree-to-manage-the-settings)
- [<span data-ttu-id="7e4b7-109">使用 DAO 的 SetOption 方法</span><span class="sxs-lookup"><span data-stu-id="7e4b7-109">Using the SetOption method from DAO</span></span>](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/using-the-setoption-method-from-dao)
- [<span data-ttu-id="7e4b7-110">使用 for Access 的 Microsoft OLE DB 提供程序中的连接属性</span><span class="sxs-lookup"><span data-stu-id="7e4b7-110">Using the Connection properties in the Microsoft OLE DB Provider for Access</span></span>](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/using-the-connection-properties-in-the-microsoft-ole-db-provider-for-access)

