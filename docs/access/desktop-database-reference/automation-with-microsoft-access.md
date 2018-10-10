---
title: Microsoft Access 的“自动化”功能
TOCTitle: Automation with Microsoft Access
ms:assetid: 39fde349-3ba3-7c7a-3c92-316641dc8712
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192643(v=office.15)
ms:contentKeyID: 48544258
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm13783
f1_categories:
- Office.Version=v15
ms.openlocfilehash: bd0e230d2b4c31d497e913e8e1ccf4d2172402e9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467541"
---
# <a name="automation-with-microsoft-access"></a><span data-ttu-id="6d4ef-102">Microsoft Access 的“自动化”功能</span><span class="sxs-lookup"><span data-stu-id="6d4ef-102">Automation with Microsoft Access</span></span>


<span data-ttu-id="6d4ef-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6d4ef-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6d4ef-p101">Microsoft Access 是一种支持自动化功能的 COM 组件（以前，自动化称为“OLE 自动化”）。Microsoft Access 以两种方式支持“自动化”。可以从 Microsoft Access 中使用由其他组件所提供的对象，Microsoft Access 也可以将自己的对象提供给其他 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-p101">Microsoft Access is a COM component that supports Automation, formerly called OLE Automation. Microsoft Access supports Automation in two ways. From Microsoft Access, you can work with objects supplied by another component. Microsoft Access also supplies its objects to other COM components.</span></span>

<span data-ttu-id="6d4ef-108">您可以使用**New**关键字或**CreateObject**方法创建一个组件的新实例。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-108">You can use the **New** keyword or the **CreateObject** method to create a new instance of a component.</span></span> <span data-ttu-id="6d4ef-109">**GetObject**方法可用于将变量分配给组件的现有实例。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-109">You can use the **GetObject** method to assign a variable to an existing instance of a component.</span></span>

<span data-ttu-id="6d4ef-p103">在 Microsoft Access 中通过“自动化”功能使用其他组件时，可以通过设置对组件类型库的引用来改善性能。Microsoft Access 还包含对象浏览器工具，可用于查看其他组件的类型库中的对象以及它们的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-p103">In Microsoft Access, you can set a reference to a component's type library to improve performance when you work with that component through Automation. Microsoft Access also includes the Object Browser, a tool that enables you to view objects in another component's type library, as well as their methods and properties.</span></span>

<span data-ttu-id="6d4ef-112">在 Microsoft Access 类型库提供给其他组件的 Microsoft Access 对象的信息。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-112">The Microsoft Access type library provides information about Microsoft Access objects to other components.</span></span> <span data-ttu-id="6d4ef-113">您可以向 Microsoft Access[设置对](https://msdn.microsoft.com/library/ff194944\(v=office.15\))类型库从组件并在对象浏览器中查看其对象。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-113">You can [set a reference](https://msdn.microsoft.com/library/ff194944\(v=office.15\)) to the Microsoft Access type library from a component and view its objects in the Object Browser.</span></span>

<span data-ttu-id="6d4ef-114">若要使用通过自动化的 Microsoft Access 对象，必须创建 Microsoft Access**[应用程序](https://msdn.microsoft.com/library/ff821758\(v=office.15\))** 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-114">To work with Microsoft Access objects through Automation, you must create an instance of the Microsoft Access **[Application](https://msdn.microsoft.com/library/ff821758\(v=office.15\))** object.</span></span> <span data-ttu-id="6d4ef-115">例如，假设您想要在 Microsoft Access 窗体或报表中显示 Microsoft Excel 中的数据。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-115">For example, suppose you want to display data from Microsoft Excel in a Microsoft Access form or report.</span></span> <span data-ttu-id="6d4ef-116">若要启动从 Microsoft Excel 的 Microsoft Access，您可以使用**New**关键字创建 Microsoft Access**应用程序**对象的实例。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-116">To launch Microsoft Access from Microsoft Excel, you can use the **New** keyword to create an instance of the Microsoft Access **Application** object.</span></span> <span data-ttu-id="6d4ef-117">您还可以使用**CreateObject**方法创建的新实例的 Microsoft Access**应用程序**对象，或者您可以使用**GetObject**方法以指向 Microsoft Access 的现有实例的一个对象变量。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-117">You can also use the **CreateObject** method to create a new instance of the Microsoft Access **Application** object, or you can use the **GetObject** method to point an object variable to an existing instance of Microsoft Access.</span></span> <span data-ttu-id="6d4ef-118">检查您的组件的文档，以确定它支持哪些语法。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-118">Check your component's documentation to determine which syntax it supports.</span></span>

<span data-ttu-id="6d4ef-119">一旦启动实例 Microsoft Access 中，如果您希望控制 Microsoft Access 中的任何对象，您必须打开数据库或项目 (.adp) 在 Microsoft Access 窗口中使用**[OpenCurrentDatabase](https://msdn.microsoft.com/library/ff837226\(v=office.15\))** 或**[NewCurrentDatabase](https://msdn.microsoft.com/library/ff195271\(v=office.15\))** 方法的数据库或项目使用**[OpenAccessProject](https://msdn.microsoft.com/library/ff837249\(v=office.15\))** 或**[NewAccessProject](https://msdn.microsoft.com/library/ff835758\(v=office.15\))** 方法。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-119">Once you've launched an instance of Microsoft Access, if you want to control any Microsoft Access objects, you must open a database or project (.adp) in the Microsoft Access window by using either the **[OpenCurrentDatabase](https://msdn.microsoft.com/library/ff837226\(v=office.15\))** or the **[NewCurrentDatabase](https://msdn.microsoft.com/library/ff195271\(v=office.15\))** method for a database or by using the **[OpenAccessProject](https://msdn.microsoft.com/library/ff837249\(v=office.15\))** or the **[NewAccessProject](https://msdn.microsoft.com/library/ff835758\(v=office.15\))** method for a project.</span></span>

<span data-ttu-id="6d4ef-120">如果您已打开仅作为一种使用 Microsoft DAO 提供数据访问对象的 Microsoft Access，您不需要在 Microsoft Access 窗口中打开数据库。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-120">If you've opened Microsoft Access only as a means of using the Data Access Objects provided by Microsoft DAO, then you don't need to open a database in the Microsoft Access window.</span></span> <span data-ttu-id="6d4ef-121">自动化操作期间，可以在 Microsoft Office 12.0 Access 数据库引擎对象库对象库中使用 Microsoft Access**应用程序**对象的访问对象的**[DBEngine](https://msdn.microsoft.com/library/ff821724\(v=office.15\))** 属性。</span><span class="sxs-lookup"><span data-stu-id="6d4ef-121">You can use the **[DBEngine](https://msdn.microsoft.com/library/ff821724\(v=office.15\))** property of the Microsoft Access **Application** object to access objects in the Microsoft Office 12.0 Access Database Engine Object Library object library during an Automation operation.</span></span>

