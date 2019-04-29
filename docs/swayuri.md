---
title: SwayURI
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 11daa75b-87fc-4e63-8e02-09ab9307c8f8
ms.date: 01/28/2016
description: 使用 sway URI 方案打开 sway 应用程序, 并查看或编辑 sway。
ms.openlocfilehash: 04848ef1de2777d916d8dd8dd381e6d5f66310d6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415311"
---
# <a name="sway-uri-scheme"></a>Sway URI 方案

此文档定义了适用于 Windows 的 Sway 应用程序的统一资源标识符 (uri) 的格式。 您可以使用此 URI 方案调用具有各种命令的 Sway 应用程序。

## <a name="sway-uri-scheme-syntax"></a>Sway URI 方案语法

以下是 URI 方案语法:

`<ms-sway>:<command-argument>`

- `<ms-sway>`&ndash;指示 Sway 是要调用的应用程序。 安装了适用于 windows 的 Sway `ms-sway`后, 会向 windows 注册为 sway 处理程序。
- `<command-argument>`&ndash;一个 URI 可能有一个或多个命令参数, 以与号 (`&`) 字符分隔。 当 URI 中包含多个 command 参数时, 与号 (`&`) 字符必须将每个命令参数与以下命令参数分隔开。 命令参数根据方案的不同而不同。 

## <a name="command-arguments"></a>命令参数

可以将多个命令参数作为 Sway URL 方案的一部分包含在内。 这些命令参数不是必需的。 如果不包括命令参数, 则会调用 Sway 应用程序。

|Command 参数名称|说明|类型|可能的值|是否必需？|
|:-----|:-----|:-----|:-----|:-----|
|**id**|Sway 的唯一标识符。 用于指示要打开的 Sway。|String|Sway 的有效唯一标识符。 id 始终是 Sway URL 的一部分。<br/><br/>例如, 对于以下 Sway `https://sway.com/dBheQgVZ1RQBfiQU`, id 为。 `dBheQgVZ1RQBfiQU`<br/><br/>如果与 Sway 应用程序关联的用户帐户具有编辑权限, 应用程序将在编辑模式下打开 Sway。 否则, 应用程序将在查看模式下打开 Sway。|否|
|**mode**|打开特定 Sway 时应使用的模式, 无论是编辑还是查看。|String|edit<br/>view<br/><br/>**注意**: 如果未指定**id** , 则忽略此命令参数。|否|
|**auth_upn**|打开 Sway 时要使用的帐户。|String|有效的电子邮件地址。<br/><br/>如果指定的电子邮件地址未与 Sway 帐户关联, 则 Sway 会要求用户以指定用户的帐户登录。<br/><br/>如果有多个帐户与 Sway 应用程序相关联, 并且存在指定的电子邮件地址, 则 Sway 应用程序将在调用时切换为使用该帐户。|否|
|**auth\_pvr**|用于打开 Sway&mdash;的帐户类型 (Microsoft 帐户或 azure Active Directory 帐户 (azure AD))。|String|WindowsLiveId –指定**身份验证\_upn**帐户是 Microsoft 帐户。<br/><br/>OrgId –指定**身份验证\_upn**帐户是 Azure AD 帐户。<br/><br/>如果未指定任何**auth\_upn** , 则忽略此命令参数。|否|
|**调用\_应用程序**|用于调用 Sway 的 Windows 应用程序的名称。|String|用于通过 sway URL 方案调用 Sway 的 Windows 应用程序的友好名称。<br/><br/>此命令参数的目的在于遥测和跟踪。|否|

## <a name="uri-scheme-semantics"></a>URI 方案语义

该`<ms-sway>`方案定义用于打开 sway 或调用 sway 应用程序的 URI 语法。 该方案定义了几个命令参数, 可用于执行以下操作: 

- 打开 Sway 应用程序&ndash;无需指定任何命令参数。 

- 打开 sway 以在 Sway 应用程序&ndash;中查看需要指定的 " **id** " 和 "**模式**" 设置为 "查看"。 

- 打开 sway 以在 Sway 应用程序&ndash;中进行编辑。需要指定将设置为要编辑的**id**和**模式**。 我们建议您同时包含**auth\_upn**和**auth\_pvr** , 以帮助确保在打开 Sway 时使用具有编辑权限的正确帐户。  

## <a name="example"></a>示例

`ms-sway:id=CyrvEYLmFKi1B2_I&auth_upn=account@email.com&auth_pvr=WindowsLiveId&invoking_app=MyApp` 


