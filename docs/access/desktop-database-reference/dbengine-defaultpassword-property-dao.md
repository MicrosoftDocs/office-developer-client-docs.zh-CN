---
title: DBEngine.DefaultPassword Property (DAO)
TOCTitle: DefaultPassword Property
ms:assetid: 189e34f3-d573-c75f-8be2-d98c50df8a52
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845616(v=office.15)
ms:contentKeyID: 48543478
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b5b1195b4217ca72374402b361b09d540583bf06
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468852"
---
# <a name="dbenginedefaultpassword-property-dao"></a><span data-ttu-id="a886e-102">DBEngine.DefaultPassword Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="a886e-102">DBEngine.DefaultPassword Property (DAO)</span></span>


<span data-ttu-id="a886e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a886e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a886e-p101">设置初始化 **Workspace** 时创建其默认值所使用的密码。可读/写 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="a886e-p101">Sets the password used to create the default **Workspace** when it is initialized. Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="a886e-106">语法</span><span class="sxs-lookup"><span data-stu-id="a886e-106">Syntax</span></span>

<span data-ttu-id="a886e-107">*表达式*。DefaultPassword</span><span class="sxs-lookup"><span data-stu-id="a886e-107">*expression* .DefaultPassword</span></span>

<span data-ttu-id="a886e-108">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="a886e-108">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a886e-109">注解</span><span class="sxs-lookup"><span data-stu-id="a886e-109">Remarks</span></span>

<span data-ttu-id="a886e-p102">**DefaultPassword** 的设置为 String 数据类型，其最大长度为 20 个字符。它可以包含除 ASCII 0 外的任何字符。</span><span class="sxs-lookup"><span data-stu-id="a886e-p102">The setting for **DefaultPassword** is a String data type that can be up to 20 characters long. It can contain any character except ASCII 0.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a886e-p103">[!注释] 使用同时包含大小写字母、数字和符号的强密码。弱密码不混合使用这些元素。例如，强密码：Y6dh!et5。弱密码：House27。请使用可以记住的强密码，这样就不必记录密码了。</span><span class="sxs-lookup"><span data-stu-id="a886e-p103">Use strong passwords that combine upper- and lowercase letters, numbers, and symbols. Weak passwords don't mix these elements. Strong password: Y6dh!et5. Weak password: House27. Use a strong password that you can remember so that you don't have to write it down.</span></span></P>



<span data-ttu-id="a886e-117">默认情况下， **DefaultUser** 属性将设置为"admin"，而 **DefaultPassword** 属性将设置为零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="a886e-117">By default, the **DefaultUser** property is set to "admin" and the **DefaultPassword** property is set to a zero-length string ("").</span></span>

<span data-ttu-id="a886e-p104">通常，可以使用 **CreateWorkspace** 方法创建一个具有给定用户名和密码的 **Workspace** 对象。但是，为了做到与早期版本的向后兼容，以及在不实现具有安全机制的数据库时提供便利，Microsoft Access 数据库引擎将根据需要自动创建一个默认的 **Workspace** 对象，前提是尚未打开一个此类对象。在这种情况下， **DefaultUser** 和 **DefaultPassword** 属性值将定义默认 **Workspace** 对象的用户和密码。</span><span class="sxs-lookup"><span data-stu-id="a886e-p104">Typically, you use the **CreateWorkspace** method to create a **Workspace** object with a given user name and password. However, for backward compatibility with earlier versions and for convenience when you don't implement a secured database, the Microsoft Access database engine automatically creates a default **Workspace** object when needed if one isn't already open. In this case, the **DefaultUser** and **DefaultPassword** property values define the user and password for the default **Workspace** object.</span></span>

<span data-ttu-id="a886e-121">若要使该属性生效，应该在调用任何 DAO 方法之前设置该属性。</span><span class="sxs-lookup"><span data-stu-id="a886e-121">For this property to take effect, you should set it before calling any DAO methods.</span></span>
