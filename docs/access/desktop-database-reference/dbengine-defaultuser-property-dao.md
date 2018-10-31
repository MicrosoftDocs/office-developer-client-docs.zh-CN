---
title: DBEngine.DefaultUser Property (DAO)
TOCTitle: DefaultUser Property
ms:assetid: 41ee0211-0794-6026-7341-3698a0b2c588
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192905(v=office.15)
ms:contentKeyID: 48544464
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053071
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 3926caa69e6a4e67bf66f2fdecde1db5fd79e2f1
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863085"
---
# <a name="dbenginedefaultuser-property-dao"></a><span data-ttu-id="6f800-102">DBEngine.DefaultUser Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="6f800-102">DBEngine.DefaultUser Property (DAO)</span></span>


<span data-ttu-id="6f800-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6f800-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6f800-p101">设置初始化 **Workspace** 时创建其默认值所使用的用户名。可读/写 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="6f800-p101">Sets the user name used to create the default **Workspace** when it is initialized. Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f800-106">语法</span><span class="sxs-lookup"><span data-stu-id="6f800-106">Syntax</span></span>

<span data-ttu-id="6f800-107">*表达式*。DefaultUser</span><span class="sxs-lookup"><span data-stu-id="6f800-107">*expression* .DefaultUser</span></span>

<span data-ttu-id="6f800-108">*表达式*一个返回**DBEngine**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="6f800-108">*expression* An expression that returns a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f800-109">注解</span><span class="sxs-lookup"><span data-stu-id="6f800-109">Remarks</span></span>

<span data-ttu-id="6f800-110">**DefaultUser**的设置是一个 String 数据类型。</span><span class="sxs-lookup"><span data-stu-id="6f800-110">The setting for **DefaultUser** is a String data type.</span></span> <span data-ttu-id="6f800-111">它可以是 1 到 20 个字符长在 Microsoft Access 工作区和它可以包含字母字符、 重音的字符、 数字、 空格和符号除外:"（引号） / （正斜杠）、 \\ （反斜杠）， \[ \] （方括号）: （冒号） |（管道） \< (较少-号)， \> (大于-号)，+ （加号） = （等于登录），;（分号），（逗号）？</span><span class="sxs-lookup"><span data-stu-id="6f800-111">It can be 1–20 characters long in Microsoft Access workspaces and it can include alphabetic characters, accented characters, numbers, spaces, and symbols except for: " (quotation marks), / (forward slash), \\ (backslash), \[ \] (brackets), : (colon), | (pipe), \< (less-than sign), \> (greater-than sign), + (plus sign), = (equal sign), ; (semicolon), , ( comma), ?</span></span> <span data-ttu-id="6f800-112">（问号） \* （星号），前导空格和控制字符 (ASCII 00 到 ASCII 31)。</span><span class="sxs-lookup"><span data-stu-id="6f800-112">(question mark), \* (asterisk), leading spaces, and control characters (ASCII 00 to ASCII 31).</span></span>


> [!NOTE]
> <span data-ttu-id="6f800-p103">[!注释] 使用同时包含大小写字母、数字和符号的强密码。弱密码不混合使用这些元素。例如，强密码：Y6dh!et5。弱密码：House27。请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="6f800-p103">Use strong passwords that combine upper- and lowercase letters, numbers, and symbols. Weak passwords don't mix these elements. Strong password: Y6dh!et5. Weak password: House27. Use a strong password that you can remember so that you don't have to write it down.</span></span>

<span data-ttu-id="6f800-118">默认情况下， **DefaultUser** 属性将设置为"admin"，而 **DefaultPassword** 属性将设置为零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="6f800-118">By default, the **DefaultUser** property is set to "admin" and the **DefaultPassword** property is set to a zero-length string ("").</span></span>

<span data-ttu-id="6f800-p104">用户名通常不区分大小写；但是，如果重新创建了一个曾经被删除的用户帐户，或者在不同的工作组中重新创建了一个用户帐户，则用户名与原始名称的大小写必须完全匹配。密码区分大小写。</span><span class="sxs-lookup"><span data-stu-id="6f800-p104">User names aren't usually case-sensitive; however, if you're re-creating a user account that was deleted or created in a different workgroup, the user name must be an exact case-sensitive match of the original name. Passwords are case-sensitive.</span></span>

<span data-ttu-id="6f800-p105">通常，可以使用 **CreateWorkspace** 方法创建一个具有给定用户名和密码的 **Workspace** 对象。但是，为了做到与早期版本的向后兼容，以及在不实现具有安全机制的数据库时提供便利，Microsoft Access 数据库引擎将根据需要自动创建一个默认的 **Workspace** 对象，前提是尚未打开一个此类对象。在这种情况下， **DefaultUser** 和 **DefaultPassword** 属性值将定义默认 **Workspace** 对象的用户和密码。</span><span class="sxs-lookup"><span data-stu-id="6f800-p105">Typically, you use the **CreateWorkspace** method to create a **Workspace** object with a given user name and password. However, for backward compatibility with earlier versions and for convenience when you don't implement a secured database, the Microsoft Access database engine automatically creates a default **Workspace** object when needed if one isn't already open. In this case, the **DefaultUser** and **DefaultPassword** property values define the user and password for the default **Workspace** object.</span></span>

<span data-ttu-id="6f800-124">若要使该属性生效，应该在调用任何 DAO 方法之前设置该属性。</span><span class="sxs-lookup"><span data-stu-id="6f800-124">For this property to take effect, you should set it before calling any DAO methods.</span></span>

