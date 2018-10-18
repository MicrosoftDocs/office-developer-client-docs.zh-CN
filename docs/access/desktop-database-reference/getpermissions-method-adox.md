---
title: GetPermissions 方法 (ADOX)
TOCTitle: GetPermissions Method (ADOX)
ms:assetid: 98a2b2b6-a8af-15ee-b052-622a6f0661b9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249683(v=office.15)
ms:contentKeyID: 48546496
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 388cbc5a69f57778d8a9a46db8d1dbec5ddf09d6
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25604959"
---
# <a name="getpermissions-method-adox"></a><span data-ttu-id="6bcd7-102">GetPermissions 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="6bcd7-102">GetPermissions Method (ADOX)</span></span>


<span data-ttu-id="6bcd7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6bcd7-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="6bcd7-104">返回组或用户对某个对象或对象容器的权限。</span><span class="sxs-lookup"><span data-stu-id="6bcd7-104">Returns the permissions for a group or user on an object or object container.</span></span>

## <a name="syntax"></a><span data-ttu-id="6bcd7-105">语法</span><span class="sxs-lookup"><span data-stu-id="6bcd7-105">Syntax</span></span>

<span data-ttu-id="6bcd7-106">*ReturnValue* = *GroupOrUser*。GetPermissions (*名称*、 *ObjectType* \[，*ObjectTypeId*\])</span><span class="sxs-lookup"><span data-stu-id="6bcd7-106">*ReturnValue* = *GroupOrUser*.GetPermissions(*Name*, *ObjectType* \[,*ObjectTypeId*\])</span></span>

<span data-ttu-id="6bcd7-107"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="6bcd7-107"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="6bcd7-108">返回值</span><span class="sxs-lookup"><span data-stu-id="6bcd7-108">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="6bcd7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6bcd7-109">Return value</span></span>
>>>>>>> <span data-ttu-id="6bcd7-110">master</span><span class="sxs-lookup"><span data-stu-id="6bcd7-110">master</span></span>

<span data-ttu-id="6bcd7-p101">返回一个指定位掩码的 **Long** 值，该位掩码包含组或用户对该对象所拥有的权限。此值可为一个或多个 [RightsEnum](rightsenum.md) 常量。</span><span class="sxs-lookup"><span data-stu-id="6bcd7-p101">Returns a **Long** value that specifies a bitmask containing the permissions that the group or user has on the object. This value can be one or more of the [RightsEnum](rightsenum.md) constants.</span></span>

## <a name="parameters"></a><span data-ttu-id="6bcd7-113">参数</span><span class="sxs-lookup"><span data-stu-id="6bcd7-113">Parameters</span></span>

  - <span data-ttu-id="6bcd7-114">*Name*</span><span class="sxs-lookup"><span data-stu-id="6bcd7-114">*Name*</span></span>

  - <span data-ttu-id="6bcd7-115">**Variant** 值，指定设置权限所针对的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="6bcd7-115">A **Variant** value that specifies the name of the object for which to set permissions.</span></span> <span data-ttu-id="6bcd7-116">如果您想要获取的对象容器的权限，请将*名称*设置为 null 值。</span><span class="sxs-lookup"><span data-stu-id="6bcd7-116">Set *Name* to a null value if you want to get the permissions for the object container.</span></span>

  - <span data-ttu-id="6bcd7-117">*ObjectType*</span><span class="sxs-lookup"><span data-stu-id="6bcd7-117">*ObjectType*</span></span>

  - <span data-ttu-id="6bcd7-118">一个类型为 **Long** 的值，可以是 [ObjectTypeEnum](objecttypeenum.md) 常量中的一个，用于指定要为其获取权限的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="6bcd7-118">A **Long** value which can be one of the [ObjectTypeEnum](objecttypeenum.md) constants, that specifies the type of the object for which to get permissions.</span></span>

  - <span data-ttu-id="6bcd7-119">*ObjectTypeId*</span><span class="sxs-lookup"><span data-stu-id="6bcd7-119">*ObjectTypeId*</span></span>

  - <span data-ttu-id="6bcd7-120">可选。</span><span class="sxs-lookup"><span data-stu-id="6bcd7-120">Optional.</span></span> <span data-ttu-id="6bcd7-121">**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="6bcd7-121">A **Variant** value that specifies the GUID for a provider object type not defined by the OLE DB specification.</span></span> <span data-ttu-id="6bcd7-122">此参数是必需的如果将*ObjectType*设置为**adPermObjProviderSpecific**;否则，它将不使用。</span><span class="sxs-lookup"><span data-stu-id="6bcd7-122">This parameter is required if *ObjectType* is set to **adPermObjProviderSpecific**; otherwise, it is not used.</span></span>

