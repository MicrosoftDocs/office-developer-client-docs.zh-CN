---
title: Append 方法（ADOX 用户）
TOCTitle: Append method (ADOX Users)
ms:assetid: b7a1128b-c6e7-2071-c914-913b6bd245ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249884(v=office.15)
ms:contentKeyID: 48547302
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d05cf352515d8fe4faa868088c9ba9cc8a024145
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297065"
---
# <a name="append-method-adox-users"></a><span data-ttu-id="c7ec5-102">Append 方法（ADOX 用户）</span><span class="sxs-lookup"><span data-stu-id="c7ec5-102">Append method (ADOX Users)</span></span>

<span data-ttu-id="c7ec5-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c7ec5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c7ec5-104">将新的 [User](user-object-adox.md) 对象添加到 [Users](users-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="c7ec5-104">Adds a new [User](user-object-adox.md) object to the [Users](users-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7ec5-105">语法</span><span class="sxs-lookup"><span data-stu-id="c7ec5-105">Syntax</span></span>

<span data-ttu-id="c7ec5-106">*用户*。追加*用户*\[、*密码*\]</span><span class="sxs-lookup"><span data-stu-id="c7ec5-106">*Users*.Append*User*\[,*Password*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="c7ec5-107">参数</span><span class="sxs-lookup"><span data-stu-id="c7ec5-107">Parameters</span></span>

|<span data-ttu-id="c7ec5-108">参数</span><span class="sxs-lookup"><span data-stu-id="c7ec5-108">Parameter</span></span>|<span data-ttu-id="c7ec5-109">描述</span><span class="sxs-lookup"><span data-stu-id="c7ec5-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="c7ec5-110">*User*</span><span class="sxs-lookup"><span data-stu-id="c7ec5-110">*User*</span></span> |<span data-ttu-id="c7ec5-111">一个 **Variant** 值，包含对要追加的 **User** 对象的引用，或者是要创建并追加的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="c7ec5-111">A **Variant** value that contains the **User** object to append or the name of the user to create and append.</span></span>|
|<span data-ttu-id="c7ec5-112">*Password*</span><span class="sxs-lookup"><span data-stu-id="c7ec5-112">*Password*</span></span> |<span data-ttu-id="c7ec5-p101">可选。包含该用户的密码的 **String** 值。*Password* 参数对应于 **User** 对象的 [ChangePassword](changepassword-method-adox.md) 方法所指定的值。</span><span class="sxs-lookup"><span data-stu-id="c7ec5-p101">Optional. A **String** value that contains the password for the user. The *Password* parameter corresponds to the value specified by the [ChangePassword](changepassword-method-adox.md) method of a **User** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c7ec5-116">注解</span><span class="sxs-lookup"><span data-stu-id="c7ec5-116">Remarks</span></span>

<span data-ttu-id="c7ec5-p102">**Catalog** 的 [Users](catalog-object-adox.md) 集合表示该目录的所有用户。 **Group** 的 [Users](group-object-adox.md) 集合仅表示在该特定组中有成员资格的用户。</span><span class="sxs-lookup"><span data-stu-id="c7ec5-p102">The **Users** collection of a [Catalog](catalog-object-adox.md) represents all the catalog's users. The **Users** collection for a [Group](group-object-adox.md) represents only the users that have a membership in the specific group.</span></span>

<span data-ttu-id="c7ec5-119">如果提供程序不支持创建用户，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="c7ec5-119">An error will occur if the provider does not support creating users.</span></span>

> [!NOTE]
> <span data-ttu-id="c7ec5-120">[!注释] 在将 **User** 对象追加到 **Group** 对象的 **Users** 集合之前， **Catalog** 的 [Users](name-property-adox.md) 集合中必须存在具有与要追加的 **User** 对象相同 **Name** 的 User 对象。</span><span class="sxs-lookup"><span data-stu-id="c7ec5-120">Before appending a **User** object to the **Users** collection of a **Group** object, a **User** object with the same [Name](name-property-adox.md) as the one to be appended must already exist in the **Users** collection of the **Catalog**.</span></span>


