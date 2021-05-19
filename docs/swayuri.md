---
title: SwayURI
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 11daa75b-87fc-4e63-8e02-09ab9307c8f8
ms.date: 01/28/2016
description: 使用 Sway URI 方案打开 Sway 应用程序并查看或编辑 Sway。
ms.openlocfilehash: 04848ef1de2777d916d8dd8dd381e6d5f66310d6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415311"
---
# <a name="sway-uri-scheme"></a>Sway URI 方案

本文档为 Sway 应用程序定义统一资源标识符 (URI) URI 的格式Windows。 可以使用此 URI 方案通过各种命令调用 Sway 应用程序。

## <a name="sway-uri-scheme-syntax"></a>Sway URI 方案语法

以下是 URI 方案语法：

`<ms-sway>:<command-argument>`

- `<ms-sway>`&ndash;指示 Sway 是要调用的应用程序。 安装 Sway for Windows 时，会向 Windows `ms-sway` 注册为 Sway 处理程序。
- `<command-argument>`URI 可能有一个或多个命令参数，用与号分隔 &ndash; () `&` 字符。 当一个 URI 中包括多个命令参数时， () 字符必须将每个命令参数与 `&` 以下命令参数分开。 命令参数因方案而异。 

## <a name="command-arguments"></a>命令参数

多个命令参数可包含在 Sway URL 方案中。 这些命令参数不是必需的。 如果不包括命令参数，将调用 Sway 应用程序。

|命令参数名称|说明|类型|可能的值|是否必需？|
|:-----|:-----|:-----|:-----|:-----|
|**id**|Sway 的唯一标识符。 用于指示要打开的 Sway。|String|Sway 的有效唯一标识符。 id 始终是 Sway URL 的一部分。<br/><br/>例如，对于以下 `https://sway.com/dBheQgVZ1RQBfiQU` Sway，id 为 `dBheQgVZ1RQBfiQU` 。<br/><br/>如果与 Sway 应用程序关联的用户帐户具有编辑权限，应用程序将在编辑模式下打开 Sway。 否则，应用程序将在视图模式下打开 Sway。|否|
|**mode**|打开特定 Sway 的模式，无论是用于编辑还是查看。|String|edit<br/>view<br/><br/>**注意**：如果 **未指定 id，** 则忽略此命令参数。|否|
|**auth_upn**|打开 Sway 时使用的帐户。|String|有效的电子邮件地址。<br/><br/>如果指定的电子邮件地址未与 Sway 帐户关联，Sway 将要求用户以指定用户登录。<br/><br/>如果多个帐户与 Sway 应用程序关联且存在指定的电子邮件地址，则 Sway 应用程序将在调用时切换到使用该帐户。|否|
|**auth \_ pvr**|用于打开 Microsoft 帐户或 Azure AD Azure Active Directory Sway (&mdash; 的帐户) 。|String|WindowsLiveId – 指定 **身份验证 \_ upn** 帐户是一个 Microsoft 帐户。<br/><br/>OrgId – 指定 **身份验证 \_ upn** 帐户是 Azure AD 帐户。<br/><br/>如果 **未指定身份验证 \_ upn，** 则忽略此命令参数。|否|
|**调用 \_ 应用**|用于调用 Sway Windows应用程序的名称。|String|用于通过 Sway URL Windows Sway 的应用程序的友好名称。<br/><br/>此命令参数用于遥测和跟踪。|否|

## <a name="uri-scheme-semantics"></a>URI 方案语义

方案 `<ms-sway>` 定义用于打开 Sway 或调用 Sway 应用程序的 URI 语法。 方案定义多个命令参数，可用于执行以下操作： 

- 打开 Sway 应用程序 &ndash; 不需要指定命令参数。 

- 打开 Sway 以在 Sway 应用程序中查看 需要指定要查看的 &ndash; **id** 和模式。 

- 在 Sway 应用程序中打开 Sway 进行编辑 需要指定要编辑的 &ndash; **id** 和模式。 我们还建议您包括 **auth \_ upn** 和 **auth \_ pvr，** 以帮助确保在打开 Sway 时使用具有编辑权限的合适帐户。  

## <a name="example"></a>示例

`ms-sway:id=CyrvEYLmFKi1B2_I&auth_upn=account@email.com&auth_pvr=WindowsLiveId&invoking_app=MyApp` 


