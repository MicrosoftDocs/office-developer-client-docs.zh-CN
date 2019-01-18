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
localization_priority: Normal
ms.openlocfilehash: f14f9f2d028bb8a9a8e71bc9d7b97ea5672466f1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717627"
---
# <a name="dbengineinipath-property-dao"></a>DBEngine.IniPath 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回与包含了 Microsoft Access 数据库引擎值的 Windows 注册表项有关的信息（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。IniPath

*表达式*一个代表**DBEngine**对象的变量。

## <a name="remarks"></a>备注

您可以与 Windows 注册表中配置 Microsoft Access 数据库引擎。 可以使用注册表设置各种选项，例如可安装的 ISAM DLL。

若要使此选项产生任何作用，必须在应用程序调用其他任何 DAO 代码之前，设置 **IniPath** 属性。此设置的作用范围仅限于您的应用程序，并且在重新启动应用程序前不能更改。

还可以使用注册表为某些可安装 ISAM 数据库驱动程序提供初始化参数。例如，要使用 Paradox 4.0 版，可将 **IniPath** 属性设置为包含了相应参数的注册表的一部分。

此属性识别任一 HKEY\_本地\_计算机或 HKEY\_本地\_用户。 如果提供没有根键，则默认值是 HKEY\_本地\_计算机。

