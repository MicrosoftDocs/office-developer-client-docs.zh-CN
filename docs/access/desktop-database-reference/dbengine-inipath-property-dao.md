---
title: DBEngine.IniPath 属性 (DAO)
TOCTitle: IniPath Property
ms:assetid: b18cace5-4e53-d011-6373-f4ac64556fd4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822009(v=office.15)
ms:contentKeyID: 48547151
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053070
f1_categories:
- Office.Version=v15
ms.openlocfilehash: fd744f10d212d8ff0f7c78ca72781869ccdcd57e
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928759"
---
# <a name="dbengineinipath-property-dao"></a><span data-ttu-id="7bba6-102">DBEngine.IniPath 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="7bba6-102">DBEngine.IniPath property (DAO)</span></span>


<span data-ttu-id="7bba6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7bba6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7bba6-104">设置或返回与包含了 Microsoft Access 数据库引擎值的 Windows 注册表项有关的信息（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="7bba6-104">Sets or returns information about the Windows Registry key that contains values for the Microsoft Access database engine (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="7bba6-105">语法</span><span class="sxs-lookup"><span data-stu-id="7bba6-105">Syntax</span></span>

<span data-ttu-id="7bba6-106">*表达式*。IniPath</span><span class="sxs-lookup"><span data-stu-id="7bba6-106">*expression* .IniPath</span></span>

<span data-ttu-id="7bba6-107">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="7bba6-107">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="7bba6-108">注解</span><span class="sxs-lookup"><span data-stu-id="7bba6-108">Remarks</span></span>

<span data-ttu-id="7bba6-p101">可以使用 Windows 注册表配置 Microsoft Access 数据库引擎。可以使用注册表设置各种选项，例如可安装的 ISAM DLL。</span><span class="sxs-lookup"><span data-stu-id="7bba6-p101">You can configure the Microsoft Access databse engine with the Windows Registry. You can use the Registry to set options, such as installable ISAM DLLs.</span></span>

<span data-ttu-id="7bba6-p102">若要使此选项产生任何作用，必须在应用程序调用其他任何 DAO 代码之前，设置 **IniPath** 属性。此设置的作用范围仅限于您的应用程序，并且在重新启动应用程序前不能更改。</span><span class="sxs-lookup"><span data-stu-id="7bba6-p102">For this option to have any effect, you must set the **IniPath** property before your application invokes any other DAO code. The scope of this setting is limited to your application and can't be changed without restarting your application.</span></span>

<span data-ttu-id="7bba6-p103">还可以使用注册表为某些可安装 ISAM 数据库驱动程序提供初始化参数。例如，要使用 Paradox 4.0 版，可将 **IniPath** 属性设置为包含了相应参数的注册表的一部分。</span><span class="sxs-lookup"><span data-stu-id="7bba6-p103">You also use the Registry to provide initialization parameters for some installable ISAM database drivers. For example, to use Paradox version 4.0, set the **IniPath** property to a part of the Registry containing the appropriate parameters.</span></span>

<span data-ttu-id="7bba6-115">此属性识别任一 HKEY\_本地\_计算机或 HKEY\_本地\_用户。</span><span class="sxs-lookup"><span data-stu-id="7bba6-115">This property recognizes either HKEY\_LOCAL\_MACHINE or HKEY\_LOCAL\_USER.</span></span> <span data-ttu-id="7bba6-116">如果提供没有根键，则默认值是 HKEY\_本地\_计算机。</span><span class="sxs-lookup"><span data-stu-id="7bba6-116">If no root key is supplied, the default is HKEY\_LOCAL\_MACHINE.</span></span>

