FROM ghcr.io/wg-easy/wg-easy:15

# Add tools required by the HA wrapper and switch firewall backend to nftables
RUN apk add --no-cache jq bash iproute2 curl && \
    update-alternatives \
      --install /usr/sbin/iptables iptables /usr/sbin/iptables-nft 20 \
      --slave /usr/sbin/iptables-restore iptables-restore /usr/sbin/iptables-nft-restore \
      --slave /usr/sbin/iptables-save iptables-save /usr/sbin/iptables-nft-save && \
    update-alternatives \
      --install /usr/sbin/ip6tables ip6tables /usr/sbin/ip6tables-nft 20 \
      --slave /usr/sbin/ip6tables-restore ip6tables-restore /usr/sbin/ip6tables-nft-restore \
      --slave /usr/sbin/ip6tables-save ip6tables-save /usr/sbin/ip6tables-nft-save && \
    update-alternatives --set iptables /usr/sbin/iptables-nft && \
    update-alternatives --set ip6tables /usr/sbin/ip6tables-nft && \
    iptables --version && \
    ip6tables --version

COPY rootfs/run.sh /run.sh
RUN chmod +x /run.sh

CMD [ "/run.sh" ]