---
title: GetPermissions 方法 (ADOX)
TOCTitle: GetPermissions method (ADOX)
ms:assetid: 98a2b2b6-a8af-15ee-b052-622a6f0661b9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249683(v=office.15)
ms:contentKeyID: 48546496
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aa5dda3c8e2ee8251fc54f4ff3bc12be0aca5002
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292242"
---
# <a name="getpermissions-method-adox"></a><span data-ttu-id="493dd-102">GetPermissions 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="493dd-102">GetPermissions method (ADOX)</span></span>

<span data-ttu-id="493dd-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="493dd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="493dd-104">返回组或用户对某个对象或对象容器的权限。</span><span class="sxs-lookup"><span data-stu-id="493dd-104">Returns the permissions for a group or user on an object or object container.</span></span>

## <a name="syntax"></a><span data-ttu-id="493dd-105">语法</span><span class="sxs-lookup"><span data-stu-id="493dd-105">Syntax</span></span>

<span data-ttu-id="493dd-106">*ReturnValue* = *GroupOrUser*。GetPermissions (*Name*、 *ObjectType* \[、*ObjectTypeId*\])</span><span class="sxs-lookup"><span data-stu-id="493dd-106">*ReturnValue* = *GroupOrUser*.GetPermissions(*Name*, *ObjectType* \[,*ObjectTypeId*\])</span></span>

## <a name="return-value"></a><span data-ttu-id="493dd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="493dd-107">Return value</span></span>

<span data-ttu-id="493dd-p101">返回一个指定位掩码的 **Long** 值，该位掩码包含组或用户对该对象所拥有的权限。此值可为一个或多个 [RightsEnum](rightsenum.md) 常量。</span><span class="sxs-lookup"><span data-stu-id="493dd-p101">Returns a **Long** value that specifies a bitmask containing the permissions that the group or user has on the object. This value can be one or more of the [RightsEnum](rightsenum.md) constants.</span></span>

## <a name="parameters"></a><span data-ttu-id="493dd-110">参数</span><span class="sxs-lookup"><span data-stu-id="493dd-110">Parameters</span></span>

|<span data-ttu-id="493dd-111">参数</span><span class="sxs-lookup"><span data-stu-id="493dd-111">Parameter</span></span>|<span data-ttu-id="493dd-112">描述</span><span class="sxs-lookup"><span data-stu-id="493dd-112">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="493dd-113">*Name*</span><span class="sxs-lookup"><span data-stu-id="493dd-113">*Name*</span></span> |<span data-ttu-id="493dd-p102">**Variant** 值，指定设置权限所针对的对象的名称。若要获取对对象容器的权限，则将 *Name* 设置为 null 值。</span><span class="sxs-lookup"><span data-stu-id="493dd-p102">A **Variant** value that specifies the name of the object for which to set permissions. Set *Name* to a null value if you want to get the permissions for the object container.</span></span>|
|<span data-ttu-id="493dd-116">*ObjectType*</span><span class="sxs-lookup"><span data-stu-id="493dd-116">*ObjectType*</span></span> |<span data-ttu-id="493dd-117">一个类型为 **Long** 的值，可以是 [ObjectTypeEnum](objecttypeenum.md) 常量中的一个，用于指定要为其获取权限的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="493dd-117">A **Long** value which can be one of the [ObjectTypeEnum](objecttypeenum.md) constants, that specifies the type of the object for which to get permissions.</span></span>|
|<span data-ttu-id="493dd-118">*ObjectTypeId*</span><span class="sxs-lookup"><span data-stu-id="493dd-118">*ObjectTypeId*</span></span> |<span data-ttu-id="493dd-p103">可选。**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。如果 *ObjectType* 设置为 **adPermObjProviderSpecific**，则必须使用此参数；否则不使用它。</span><span class="sxs-lookup"><span data-stu-id="493dd-p103">Optional. A **Variant** value that specifies the GUID for a provider object type not defined by the OLE DB specification. This parameter is required if *ObjectType* is set to **adPermObjProviderSpecific**; otherwise, it is not used.</span></span>|

