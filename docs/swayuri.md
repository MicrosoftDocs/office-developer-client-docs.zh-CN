---
title: SwayURI
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 11daa75b-87fc-4e63-8e02-09ab9307c8f8
ms.date: 01/28/2016
description: 使用 Sway URI 方案打开 Sway 应用程序并查看或编辑 Sway。
ms.openlocfilehash: 7a820339abcd666e7e1b9ad584cd152ca8fd4f68
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779622"
---
# <a name="sway-uri-scheme"></a>Sway URI 方案

本文档为 Windows 的 Sway 应用程序定义统一资源标识符 (Uri) 的格式。 您可以使用此 URI 方案调用各种命令的 Sway 应用程序。

## <a name="sway-uri-scheme-syntax"></a>Sway URI 方案语法

以下是 URI 方案语法：

`<ms-sway>:<command-argument>`

- `<ms-sway>`&ndash;指示 Sway 要调用的应用程序。 安装用于 Windows 的 Sway 时，`ms-sway`注册 Windows 为 Sway 处理程序。
- `<command-argument>`&ndash; URI 可能具有一个或多个命令参数，分隔连字符 (`&`) 字符。 在 URI & 时包含多个命令参数 (`&`) 字符必须与以下命令参数分开每个命令参数。 命令参数根据方案而有所不同。 

## <a name="command-arguments"></a>命令参数

多个命令参数可以是作为 Sway URL 方案的一部分包含。 这些命令参数不是必需的。 如果不包括命令参数，则调用 Sway 应用程序。

|命令参数名称|说明|类型|可能的值|是否必需？|
|:-----|:-----|:-----|:-----|:-----|
|**id**|Sway 唯一标识符。 用于指示 Sway 打开。|字符串|Sway 有效的唯一标识符。 Id 始终是 Sway 的 URL 的一部分。<br/><br/>例如，对于以下 Sway `https://sway.com/dBheQgVZ1RQBfiQU`，id 是`dBheQgVZ1RQBfiQU`。<br/><br/>如果 Sway 应用程序关联的用户帐户具有编辑权限，应用程序将在编辑模式下打开 Sway。 否则，应用程序在查看模式中打开 Sway。|否|
|**mode**|将在其中特定 Sway 应打开，以进行编辑或查看模式。|字符串|edit<br/>view<br/><br/>**注意**： 如果指定无**id** ，则此命令参数被忽略。|否|
|**auth_upn**|要打开 Sway 时使用的帐户。|字符串|一个有效的电子邮件地址。<br/><br/>如果指定的电子邮件地址不使用 Sway 帐户相关联，Sway 询问用户以指定的用户身份登录。<br/><br/>如果多个帐户相关联的 Sway 应用程序，并且存在指定的电子邮件地址的 Sway 应用程序将切换到使用该帐户时调用。|否|
|**身份验证\_pvr**|用于打开 Sway 帐户的类型&mdash;是 Microsoft 帐户或 Azure Active Directory 帐户 (Azure AD)。|字符串|WindowsLiveId – 指定**身份验证\_upn**帐户是否为 Microsoft 帐户。<br/><br/>OrgId – 指定**身份验证\_upn**帐户是 Azure AD 帐户。<br/><br/>如果没有**身份验证\_upn**指定，则此命令参数被忽略。|否|
|**调用\_应用程序**|用于调用 Sway Windows 应用程序的名称。|字符串|用于通过 Sway URL 方案调用 Sway Windows 应用程序的友好名称。<br/><br/>此命令参数的目的是遥测和跟踪。|否|

## <a name="uri-scheme-semantics"></a>URI 方案语义

`<ms-sway>`方案定义打开 Sway 或调用 Sway 应用程序 URI 语法。 将配色方案定义多个命令参数，可用于执行下列操作： 

- 打开 Sway 应用程序&ndash;不需要指定任何命令参数。 

- Sway 应用程序中打开查看 Sway&ndash;的**id**和**模式**设置为查看需要指定。 

- 打开进行编辑 Sway 应用程序中的 Sway&ndash;的**id**和**模式**设置为编辑需要指定。 我们建议您还包括**身份验证\_upn**和**身份验证\_pvr**以帮助确保打开 Sway 时使用的编辑权限的右帐户。  

## <a name="example"></a>示例

`ms-sway:id=CyrvEYLmFKi1B2_I&auth_upn=account@email.com&auth_pvr=WindowsLiveId&invoking_app=MyApp` 


