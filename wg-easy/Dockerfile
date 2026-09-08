FROM ghcr.io/wg-easy/wg-easy:15

# Add tools required by the HA wrapper
RUN apk add --no-cache jq bash iproute2 curl && \
    update-alternatives --set iptables /usr/sbin/iptables-nft && \
    update-alternatives --set ip6tables /usr/sbin/ip6tables-nft

COPY rootfs/run.sh /run.sh
RUN chmod +x /run.sh

CMD [ "/run.sh" ]