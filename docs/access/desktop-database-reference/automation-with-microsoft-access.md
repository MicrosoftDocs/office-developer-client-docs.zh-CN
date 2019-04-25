---
title: 使用 Microsoft Access 自动操作
TOCTitle: Automation with Microsoft Access
description: Microsoft Access 是一个支持自动化的 COM 组件，以前称为“OLE 自动化”。
ms:assetid: 39fde349-3ba3-7c7a-3c92-316641dc8712
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192643(v=office.15)
ms:contentKeyID: 48544258
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm13783
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 9635cdb2a06f610f42e4aa9fc9f998719aebb986
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296960"
---
# <a name="automation-with-microsoft-access"></a><span data-ttu-id="184e8-103">使用 Microsoft Access 自动操作</span><span class="sxs-lookup"><span data-stu-id="184e8-103">Automation with Microsoft Access</span></span>

<span data-ttu-id="184e8-104">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="184e8-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="184e8-p101">Microsoft Access 是一种支持自动化功能的 COM 组件（以前，自动化称为“OLE 自动化”）。Microsoft Access 以两种方式支持“自动化”。可以从 Microsoft Access 中使用由其他组件所提供的对象，Microsoft Access 也可以将自己的对象提供给其他 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="184e8-p101">Microsoft Access is a COM component that supports Automation, formerly called OLE Automation. Microsoft Access supports Automation in two ways. From Microsoft Access, you can work with objects supplied by another component. Microsoft Access also supplies its objects to other COM components.</span></span>

<span data-ttu-id="184e8-109">可以使用 **New** 关键字或 **CreateObject** 方法来创建组件的新实例。</span><span class="sxs-lookup"><span data-stu-id="184e8-109">You can use the **New** keyword or the **CreateObject** method to create a new instance of a component. You can use the  GetObject method to assign a variable to an existing instance of a component.</span></span> <span data-ttu-id="184e8-110">可以使用 **GetObject** 方法将变量分配给组件的现有实例。</span><span class="sxs-lookup"><span data-stu-id="184e8-110">You can use the **New keyword or the CreateObject method to create a new instance of a component. You can use the  GetObject** method to assign a variable to an existing instance of a component.</span></span>

<span data-ttu-id="184e8-p103">在 Microsoft Access 中通过“自动化”功能使用其他组件时，可以通过设置对组件类型库的引用来改善性能。Microsoft Access 还包含对象浏览器工具，可用于查看其他组件的类型库中的对象以及它们的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="184e8-p103">In Microsoft Access, you can set a reference to a component's type library to improve performance when you work with that component through Automation. Microsoft Access also includes the Object Browser, a tool that enables you to view objects in another component's type library, as well as their methods and properties.</span></span>

<span data-ttu-id="184e8-113">Microsoft Access 类型库向其他组件提供有关 Microsoft Access 对象的信息。</span><span class="sxs-lookup"><span data-stu-id="184e8-113">The Microsoft Access type library provides information about Microsoft Access objects to other components.</span></span> <span data-ttu-id="184e8-114">可以从某个组件对 Microsoft Access 类型库[设置引用](https://docs.microsoft.com/office/vba/access/Concepts/Settings/set-references-to-type-libraries)，并在“对象浏览器”中查看其对象。</span><span class="sxs-lookup"><span data-stu-id="184e8-114">You can [set a reference](https://docs.microsoft.com/office/vba/access/Concepts/Settings/set-references-to-type-libraries)
 to the Microsoft Access type library from a component and view its objects in the Object Browser.</span></span>

<span data-ttu-id="184e8-115">要通过“自动化”来处理 Microsoft Access 对象，必须创建 Microsoft Access **[Application](https://docs.microsoft.com/office/vba/api/Access.Application)** 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="184e8-115">To work with Microsoft Access objects through Automation, you must create an instance of the Microsoft Access [**Application**](https://docs.microsoft.com/office/vba/api/Access.Application)
 object.</span></span> <span data-ttu-id="184e8-116">例如，假设要在 Microsoft Access 窗体或报表中显示来自 Microsoft Excel 的数据。</span><span class="sxs-lookup"><span data-stu-id="184e8-116">For example, suppose you want to display data from Microsoft Excel in a Microsoft Access form or report.</span></span> <span data-ttu-id="184e8-117">为了从 Microsoft Excel 中启动 Microsoft Access，可以使用关键字 **New** 创建 Microsoft Access **Application** 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="184e8-117">To launch Microsoft Access from Microsoft Excel, you can use the **New** keyword to create an instance of the Microsoft Access **Application** object.</span></span> <span data-ttu-id="184e8-118">您也可以使用 **CreateObject** 方法新建 Microsoft Access **Application** 对象的实例，或者还可以使用 **GetObject** 方法将对象变量指向已有的 Microsoft Access 实例。</span><span class="sxs-lookup"><span data-stu-id="184e8-118">You can also use the **CreateObject** method to create a new instance of the Microsoft Access **Application** object, or you can use the **GetObject** method to point an object variable to an existing instance of Microsoft Access.</span></span> <span data-ttu-id="184e8-119">请查阅组件文档，以确定它支持何种语法。</span><span class="sxs-lookup"><span data-stu-id="184e8-119">Check your component's documentation to determine which syntax it supports.</span></span>

<span data-ttu-id="184e8-120">启动 Microsoft Access 的实例之后，要想控制任何 Microsoft Access 对象，都必须使用数据库的 **[OpenCurrentDatabase](https://docs.microsoft.com/office/vba/api/Access.Application.OpenCurrentDatabase)** 方法或 **[NewCurrentDatabase](https://docs.microsoft.com/office/vba/api/Access.Application.NewCurrentDatabase)** 方法，或使用项目的 **[OpenAccessProject](https://docs.microsoft.com/office/vba/api/Access.Application.OpenAccessProject)** 或 **[NewAccessProject](https://docs.microsoft.com/office/vba/api/Access.Application.NewAccessProject)** 方法，在 Microsoft Access 窗口中打开数据库或项目 (.adp)。</span><span class="sxs-lookup"><span data-stu-id="184e8-120">Once you've launched an instance of Microsoft Access, if you want to control any Microsoft Access objects, you must open a database  or project (.adp) in the Microsoft Access window by using either the [**OpenCurrentDatabase**](https://docs.microsoft.com/office/vba/api/Access.Application.OpenCurrentDatabase)
 or the [**NewCurrentDatabase**](https://docs.microsoft.com/office/vba/api/Access.Application.NewCurrentDatabase)
 method for a database or by using the [**OpenAccessProject**](https://docs.microsoft.com/office/vba/api/Access.Application.OpenAccessProject)
 or the [**NewAccessProject**](https://docs.microsoft.com/office/vba/api/Access.Application.NewAccessProject)
 method for a project.</span></span>

<span data-ttu-id="184e8-121">如果你为了使用 Microsoft DAO 提供的数据访问对象而已经打开了 Microsoft Access，则不需要在 Microsoft Access 窗口中打开数据库。</span><span class="sxs-lookup"><span data-stu-id="184e8-121">If you've opened Microsoft Access only as a means of using the Data Access Objects provided by Microsoft DAO, then you don't need to open a database in the Microsoft Access window.</span></span> <span data-ttu-id="184e8-122">在“自动化”操作期间，你可以使用 Microsoft Access **Application** 对象的 **[DBEngine](https://docs.microsoft.com/office/vba/api/Access.Application.DBEngine)** 属性来访问 Microsoft Office 12.0 Access Database Engine Object Library 中的对象。</span><span class="sxs-lookup"><span data-stu-id="184e8-122">You can use the [**DBEngine**](https://docs.microsoft.com/office/vba/api/Access.Application.DBEngine)
 property of the Microsoft Access **Application** object to access objects in the Microsoft Office 12.0 Access Database Engine Object Library object library during an Automation operation.</span></span>

