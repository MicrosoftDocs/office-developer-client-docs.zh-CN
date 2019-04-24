---
title: DefaultPassword 属性 (DAO) DBEngine
TOCTitle: DefaultPassword Property
ms:assetid: 189e34f3-d573-c75f-8be2-d98c50df8a52
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845616(v=office.15)
ms:contentKeyID: 48543478
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 72e73d29129c749d5479e2c7b17827f13adb4847
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294356"
---
# <a name="dbenginedefaultpassword-property-dao"></a>DefaultPassword 属性 (DAO) DBEngine


**适用于**：Access 2013、Office 2013

设置初始化 **Workspace** 时创建其默认值所使用的密码。 可读/写 **String** 类型。

## <a name="syntax"></a>语法

*表达式*。DefaultPassword

*表达式*一个代表**DBEngine**对象的变量。

## <a name="remarks"></a>注解

**DefaultPassword** 的设置为 String 数据类型，其最大长度为 20 个字符。它可以包含除 ASCII 0 外的任何字符。


> [!NOTE]
> [!注释] 使用同时包含大小写字母、数字和符号的强密码。弱密码不混合使用这些元素。例如，强密码：Y6dh!et5。弱密码：House27。请使用可以记住的强密码，这样就不必记录密码了。

默认情况下， **DefaultUser** 属性将设置为"admin"，而 **DefaultPassword** 属性将设置为零长度字符串 ("")。

通常，可以使用 **CreateWorkspace** 方法创建一个具有给定用户名和密码的 **Workspace** 对象。但是，为了做到与早期版本的向后兼容，以及在不实现具有安全机制的数据库时提供便利，Microsoft Access 数据库引擎将根据需要自动创建一个默认的 **Workspace** 对象，前提是尚未打开一个此类对象。在这种情况下， **DefaultUser** 和 **DefaultPassword** 属性值将定义默认 **Workspace** 对象的用户和密码。

若要使该属性生效，应该在调用任何 DAO 方法之前设置该属性。

