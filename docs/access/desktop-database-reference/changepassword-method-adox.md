---
title: ChangePassword 方法 (ADOX)
TOCTitle: ChangePassword method (ADOX)
ms:assetid: 999826a5-3e6b-b6da-b8f6-d61b9a50ceca
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249690(v=office.15)
ms:contentKeyID: 48546519
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: df67774b9b38b5fbcc836a2ea0dfc17886d67107
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713090"
---
# <a name="changepassword-method-adox"></a><span data-ttu-id="24f2a-102">ChangePassword 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="24f2a-102">ChangePassword method (ADOX)</span></span>

<span data-ttu-id="24f2a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="24f2a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="24f2a-104">更改用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="24f2a-104">Changes the password for a user account.</span></span>

## <a name="syntax"></a><span data-ttu-id="24f2a-105">语法</span><span class="sxs-lookup"><span data-stu-id="24f2a-105">Syntax</span></span>

<span data-ttu-id="24f2a-106">*用户*。ChangePassword*旧密码* *NewPassword*</span><span class="sxs-lookup"><span data-stu-id="24f2a-106">*User*.ChangePassword*OldPassword*, *NewPassword*</span></span>

## <a name="parameters"></a><span data-ttu-id="24f2a-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="24f2a-107">Parameters</span></span>

|<span data-ttu-id="24f2a-108">参数</span><span class="sxs-lookup"><span data-stu-id="24f2a-108">Parameter</span></span>|<span data-ttu-id="24f2a-109">说明</span><span class="sxs-lookup"><span data-stu-id="24f2a-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="24f2a-110">*旧密码*</span><span class="sxs-lookup"><span data-stu-id="24f2a-110">*OldPassword*</span></span> |<span data-ttu-id="24f2a-p101">一个指定用户现有密码的 **String** 值。如果该用户当前没有密码，则使用空字符串 ("") 作为 *OldPassword*。</span><span class="sxs-lookup"><span data-stu-id="24f2a-p101">A **String** value that specifies the user's existing password. If the user doesn't currently have a password, use an empty string ("") for *OldPassword*.</span></span>|
|<span data-ttu-id="24f2a-113">*新密码*</span><span class="sxs-lookup"><span data-stu-id="24f2a-113">*NewPassword*</span></span> |<span data-ttu-id="24f2a-114">一个指定新密码的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="24f2a-114">A **String** value that specifies the new password.</span></span>|

## <a name="remarks"></a><span data-ttu-id="24f2a-115">备注</span><span class="sxs-lookup"><span data-stu-id="24f2a-115">Remarks</span></span>

<span data-ttu-id="24f2a-116">出于安全原因，除了新密码之外还必须指定旧密码。</span><span class="sxs-lookup"><span data-stu-id="24f2a-116">For security reasons, the old password must be specified in addition to the new password.</span></span>

<span data-ttu-id="24f2a-117">如果提供程序不支持管理受任者属性，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="24f2a-117">An error will occur if the provider does not support the administration of trustee properties.</span></span>

