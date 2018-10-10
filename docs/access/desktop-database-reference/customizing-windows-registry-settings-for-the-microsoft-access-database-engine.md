---
title: 自定义 Microsoft Access 数据库引擎的 Windows 注册表设置
TOCTitle: Customizing Windows Registry Settings for the Microsoft Access Database Engine
ms:assetid: ca7e958a-ea26-d67d-45b9-10aeb1eac96b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834346(v=office.15)
ms:contentKeyID: 48547690
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- acmain11.chm1032168
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 4a90981c936c933d2eadb191bbf0d2639cd8e641
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468126"
---
# <a name="customizing-windows-registry-settings-for-the-microsoft-access-database-engine"></a><span data-ttu-id="b877d-102">自定义 Microsoft Access 数据库引擎的 Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="b877d-102">Customizing Windows Registry Settings for the Microsoft Access Database Engine</span></span>


<span data-ttu-id="b877d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b877d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b877d-p101">如果应用程序使用 Microsoft Access 数据库引擎的默认功能不能正确地工作，那么您可能不得不根据自己的需要更改 Microsoft® Windows® 注册表中的设置。Windows 注册表也可用于调整可安装的 ISAM 和 ODBC 驱动程序的操作。</span><span class="sxs-lookup"><span data-stu-id="b877d-p101">If your application cannot work correctly with the default functionality of the Microsoft Access database engine, you may have to change the settings in the Microsoft® Windows® Registry to suit your needs. The Windows Registry can also be used to tune the operation of the installable ISAM and ODBC driver.</span></span>

<span data-ttu-id="b877d-106">自定义 Windows 注册表设置有以下四种不同的方式：</span><span class="sxs-lookup"><span data-stu-id="b877d-106">You can customize the settings in the Windows Registry in four different ways:</span></span>

<span data-ttu-id="b877d-107">[使用 Regedit.exe 覆盖默认设置 ](https://msdn.microsoft.com/library/ff193205\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="b877d-107">[Using Regedit.exe to Overwrite the Default Settings](https://msdn.microsoft.com/library/ff193205\(v=office.15\))</span></span>

<span data-ttu-id="b877d-108">[在应用程序的注册表树中创建一个分区以管理设置](https://msdn.microsoft.com/library/ff836342\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="b877d-108">[Creating a Portion in Your Application's Registry Tree to Manage the Settings](https://msdn.microsoft.com/library/ff836342\(v=office.15\))</span></span>

<span data-ttu-id="b877d-109">[使用 DAO 的 SetOption 方法](https://msdn.microsoft.com/library/ff194471\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="b877d-109">[Using the SetOption Method from DAO](https://msdn.microsoft.com/library/ff194471\(v=office.15\))</span></span>

<span data-ttu-id="b877d-110">[使用 Microsoft OLE DB Provider for Access 中的连接属性](https://msdn.microsoft.com/library/ff196356\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="b877d-110">[Using the Connection Properties in the Microsoft OLE DB Provider for Access](https://msdn.microsoft.com/library/ff196356\(v=office.15\))</span></span>

