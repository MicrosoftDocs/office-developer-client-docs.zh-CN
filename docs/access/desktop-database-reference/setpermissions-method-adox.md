---
title: SetPermissions 方法 (ADOX)
TOCTitle: SetPermissions method (ADOX)
ms:assetid: 63d1053d-fb32-456b-ae67-3a4e45aa01af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249382(v=office.15)
ms:contentKeyID: 48545274
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4f9b393e90d579c131865b112263efd0aef3216b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314579"
---
# <a name="setpermissions-method-adox"></a><span data-ttu-id="40cac-102">SetPermissions 方法 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="40cac-102">SetPermissions method (ADOX)</span></span>

<span data-ttu-id="40cac-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="40cac-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="40cac-104">指定组或用户对某个对象的权限。</span><span class="sxs-lookup"><span data-stu-id="40cac-104">Specifies the permissions for a group or user on an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="40cac-105">语法</span><span class="sxs-lookup"><span data-stu-id="40cac-105">Syntax</span></span>

<span data-ttu-id="40cac-106">*GroupOrUser*。SetPermissions*Name*、 *ObjectType*、 *Action*、 *Rights* \[、*Inherit* \] \[、*ObjectTypeId*\]</span><span class="sxs-lookup"><span data-stu-id="40cac-106">*GroupOrUser*.SetPermissions*Name*, *ObjectType*, *Action*, *Rights* \[,*Inherit*\] \[,*ObjectTypeId*\]</span></span>

## <a name="parameters"></a><span data-ttu-id="40cac-107">参数</span><span class="sxs-lookup"><span data-stu-id="40cac-107">Parameters</span></span>

|<span data-ttu-id="40cac-108">参数</span><span class="sxs-lookup"><span data-stu-id="40cac-108">Parameter</span></span>|<span data-ttu-id="40cac-109">描述</span><span class="sxs-lookup"><span data-stu-id="40cac-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="40cac-110">*Name*</span><span class="sxs-lookup"><span data-stu-id="40cac-110">*Name*</span></span> |<span data-ttu-id="40cac-111">**String** 值，指定设置权限所针对的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="40cac-111">A **String** value that specifies the name of the object for which to set permissions.</span></span>|
|<span data-ttu-id="40cac-112">*ObjectType*</span><span class="sxs-lookup"><span data-stu-id="40cac-112">*ObjectType*</span></span> |<span data-ttu-id="40cac-113">一个类型为 **Long** 的值，可以是 [ObjectTypeEnum](objecttypeenum.md) 常量中的一个，用于指定要为其获取权限的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="40cac-113">A **Long** value which can be one of the [ObjectTypeEnum](objecttypeenum.md) constants, that specifies the type of the object for which to get permissions.</span></span>|
|<span data-ttu-id="40cac-114">*Action*</span><span class="sxs-lookup"><span data-stu-id="40cac-114">*Action*</span></span> |<span data-ttu-id="40cac-115">一个可设为 **ActionEnum** 常量之一的 [Long](actionenum.md) 值，指定设置权限时要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="40cac-115">A **Long** value which can be one of the [ActionEnum](actionenum.md) constants that specifies the type of action to perform when setting permissions.</span></span>|
|<span data-ttu-id="40cac-116">*Rights*</span><span class="sxs-lookup"><span data-stu-id="40cac-116">*Rights*</span></span> |<span data-ttu-id="40cac-117">**Long** 值，可以是一个或多个 [RightsEnum](rightsenum.md) 常量的位掩码，该值表示要设置的权限。</span><span class="sxs-lookup"><span data-stu-id="40cac-117">A **Long** value which can be a bitmask of one or more of the [RightsEnum](rightsenum.md) constants, that indicates the rights to set.</span></span>|
|<span data-ttu-id="40cac-118">*Inherit*</span><span class="sxs-lookup"><span data-stu-id="40cac-118">*Inherit*</span></span> |<span data-ttu-id="40cac-p101">可选。一个可设为 **InheritTypeEnum** 常量之一的 [Long](inherittypeenum.md) 值，指定对象如何继承这些权限。默认值为 **adInheritNone** 。</span><span class="sxs-lookup"><span data-stu-id="40cac-p101">Optional. A **Long** value which can be one of the [InheritTypeEnum](inherittypeenum.md) constants, that specifies how objects will inherit these permissions. The default value is **adInheritNone**.</span></span>|
|<span data-ttu-id="40cac-122">*ObjectTypeId*</span><span class="sxs-lookup"><span data-stu-id="40cac-122">*ObjectTypeId*</span></span> |<span data-ttu-id="40cac-p102">可选。**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。如果 *ObjectType* 设置为 **adPermObjProviderSpecific**，则必须使用此参数；否则不使用它。</span><span class="sxs-lookup"><span data-stu-id="40cac-p102">Optional. A **Variant** value that specifies the GUID for a provider object type not defined by the OLE DB specification. This parameter is required if *ObjectType* is set to **adPermObjProviderSpecific**; otherwise, it is not used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="40cac-126">注解</span><span class="sxs-lookup"><span data-stu-id="40cac-126">Remarks</span></span>

<span data-ttu-id="40cac-127">如果提供程序不支持为组或用户设置访问权限，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="40cac-127">An error will occur if the provider does not support setting access rights for groups or users.</span></span>

> [!NOTE]
> <span data-ttu-id="40cac-p103">调用 **SetPermissions** 时，将 Actions 设置为 **adAccessRevoke** 会导致忽略 *Rights* 参数的任何设置。如果想让 *Rights* 参数指定的权限生效，请不要将 *Actions* 设置为 **adAccessRevoke**。</span><span class="sxs-lookup"><span data-stu-id="40cac-p103">When calling **SetPermissions**, setting Actions to **adAccessRevoke** overrides any settings of the *Rights* parameter. Do not set *Actions* to **adAccessRevoke** if you want the rights specified in the *Rights* parameter to take effect.</span></span>


