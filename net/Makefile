#
# Makefile for the linux networking.
#
# 2 Sep 2000, Christoph Hellwig <hch@infradead.org>
# Rewritten to use lists instead of if-statements.
#

obj-$(CONFIG_NET)		:= socket.o core/

tmp-$(CONFIG_COMPAT) 		:= compat.o
obj-$(CONFIG_NET)		+= $(tmp-y)

# LLC has to be linked before the files in net/802/
obj-$(CONFIG_NET)		+= ethernet/ 802/ sched/ netlink/
obj-$(CONFIG_NETFILTER)		+= netfilter/
obj-$(CONFIG_INET)		+= ipv4/
obj-$(CONFIG_UNIX)		+= unix/
obj-$(CONFIG_NET)		+= ipv6/
obj-$(CONFIG_PACKET)		+= packet/
obj-$(CONFIG_NET_KEY)		+= key/
obj-$(CONFIG_BRIDGE)		+= bridge/
obj-$(CONFIG_NET_DSA)		+= dsa/
obj-$(CONFIG_NETROM)		+= netrom/
obj-$(CONFIG_SUNRPC)		+= sunrpc/
obj-$(CONFIG_L2TP)		+= l2tp/
ifneq ($(CONFIG_VLAN_8021Q),)
obj-y				+= 8021q/
endif
obj-$(CONFIG_WIRELESS)		+= wireless/
obj-$(CONFIG_MAC80211)		+= mac80211/
obj-$(CONFIG_RFKILL)		+= rfkill/

ifeq ($(CONFIG_NET),y)
obj-$(CONFIG_SYSCTL)		+= sysctl_net.o
endif
obj-$(CONFIG_DNS_RESOLVER)	+= dns_resolver/
