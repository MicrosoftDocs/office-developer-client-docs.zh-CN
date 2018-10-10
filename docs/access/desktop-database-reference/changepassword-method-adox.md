---
title: ChangePassword 方法 (ADOX)
TOCTitle: ChangePassword Method (ADOX)
ms:assetid: 999826a5-3e6b-b6da-b8f6-d61b9a50ceca
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249690(v=office.15)
ms:contentKeyID: 48546519
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2bd2f5d87c6f90e940858ce5c6e01099c5e539d4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465863"
---
# <a name="changepassword-method-adox"></a><span data-ttu-id="afdd9-102">ChangePassword 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="afdd9-102">ChangePassword Method (ADOX)</span></span>


<span data-ttu-id="afdd9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="afdd9-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="afdd9-104">更改用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="afdd9-104">Changes the password for a user account.</span></span>

## <a name="syntax"></a><span data-ttu-id="afdd9-105">语法</span><span class="sxs-lookup"><span data-stu-id="afdd9-105">Syntax</span></span>

<span data-ttu-id="afdd9-106">*用户*。ChangePassword*旧密码* *NewPassword*</span><span class="sxs-lookup"><span data-stu-id="afdd9-106">*User*.ChangePassword*OldPassword*, *NewPassword*</span></span>

## <a name="parameters"></a><span data-ttu-id="afdd9-107">参数</span><span class="sxs-lookup"><span data-stu-id="afdd9-107">Parameters</span></span>

  - <span data-ttu-id="afdd9-108">*旧密码*</span><span class="sxs-lookup"><span data-stu-id="afdd9-108">*OldPassword*</span></span>

  - <span data-ttu-id="afdd9-p101">一个指定用户现有密码的 **String** 值。如果该用户当前没有密码，则使用空字符串 ("") 作为 *OldPassword*。</span><span class="sxs-lookup"><span data-stu-id="afdd9-p101">A **String** value that specifies the user's existing password. If the user doesn't currently have a password, use an empty string ("") for *OldPassword*.</span></span>

  - <span data-ttu-id="afdd9-111">*新密码*</span><span class="sxs-lookup"><span data-stu-id="afdd9-111">*NewPassword*</span></span>

  - <span data-ttu-id="afdd9-112">一个指定新密码的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="afdd9-112">A **String** value that specifies the new password.</span></span>

## <a name="remarks"></a><span data-ttu-id="afdd9-113">备注</span><span class="sxs-lookup"><span data-stu-id="afdd9-113">Remarks</span></span>

<span data-ttu-id="afdd9-114">出于安全原因，除了新密码之外还必须指定旧密码。</span><span class="sxs-lookup"><span data-stu-id="afdd9-114">For security reasons, the old password must be specified in addition to the new password.</span></span>

<span data-ttu-id="afdd9-115">如果提供程序不支持管理受任者属性，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="afdd9-115">An error will occur if the provider does not support the administration of trustee properties.</span></span>

