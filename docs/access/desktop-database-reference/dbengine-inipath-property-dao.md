---
title: IniPath 属性 (DAO) DBEngine
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
localization_priority: Normal
ms.openlocfilehash: f14f9f2d028bb8a9a8e71bc9d7b97ea5672466f1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294293"
---
# <a name="dbengineinipath-property-dao"></a><span data-ttu-id="a7b36-102">IniPath 属性 (DAO) DBEngine</span><span class="sxs-lookup"><span data-stu-id="a7b36-102">DBEngine.IniPath property (DAO)</span></span>


<span data-ttu-id="a7b36-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a7b36-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a7b36-104">设置或返回与包含了 Microsoft Access 数据库引擎值的 Windows 注册表项有关的信息（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="a7b36-104">Sets or returns information about the Windows Registry key that contains values for the Microsoft Access database engine (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="a7b36-105">语法</span><span class="sxs-lookup"><span data-stu-id="a7b36-105">Syntax</span></span>

<span data-ttu-id="a7b36-106">*表达式*。IniPath</span><span class="sxs-lookup"><span data-stu-id="a7b36-106">*expression* .IniPath</span></span>

<span data-ttu-id="a7b36-107">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="a7b36-107">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7b36-108">注解</span><span class="sxs-lookup"><span data-stu-id="a7b36-108">Remarks</span></span>

<span data-ttu-id="a7b36-109">您可以使用 Windows 注册表配置 Microsoft Access 数据库引擎。</span><span class="sxs-lookup"><span data-stu-id="a7b36-109">You can configure the Microsoft Access database engine with the Windows Registry.</span></span> <span data-ttu-id="a7b36-110">可以使用注册表设置各种选项，例如可安装的 ISAM DLL。</span><span class="sxs-lookup"><span data-stu-id="a7b36-110">You can use the Registry to set options, such as installable ISAM DLLs.</span></span>

<span data-ttu-id="a7b36-p102">若要使此选项产生任何作用，必须在应用程序调用其他任何 DAO 代码之前，设置 **IniPath** 属性。此设置的作用范围仅限于您的应用程序，并且在重新启动应用程序前不能更改。</span><span class="sxs-lookup"><span data-stu-id="a7b36-p102">For this option to have any effect, you must set the **IniPath** property before your application invokes any other DAO code. The scope of this setting is limited to your application and can't be changed without restarting your application.</span></span>

<span data-ttu-id="a7b36-p103">还可以使用注册表为某些可安装 ISAM 数据库驱动程序提供初始化参数。例如，要使用 Paradox 4.0 版，可将 **IniPath** 属性设置为包含了相应参数的注册表的一部分。</span><span class="sxs-lookup"><span data-stu-id="a7b36-p103">You also use the Registry to provide initialization parameters for some installable ISAM database drivers. For example, to use Paradox version 4.0, set the **IniPath** property to a part of the Registry containing the appropriate parameters.</span></span>

<span data-ttu-id="a7b36-115">此属性可识别\_HKEY 本地\_计算机或 HKEY\_本地\_用户。</span><span class="sxs-lookup"><span data-stu-id="a7b36-115">This property recognizes either HKEY\_LOCAL\_MACHINE or HKEY\_LOCAL\_USER.</span></span> <span data-ttu-id="a7b36-116">如果未提供任何根键, 则默认为 HKEY\_LOCAL\_MACHINE。</span><span class="sxs-lookup"><span data-stu-id="a7b36-116">If no root key is supplied, the default is HKEY\_LOCAL\_MACHINE.</span></span>

