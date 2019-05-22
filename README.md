Basic traefik role with sane defaults that you can apply with a one-liner:

    # Deploy with staging certificates by default to not blacklist your domain
    # in case of configuration mistake
    bigsudo yourlabs.traefik @example.com --become -v domain=example.com email=your@email

    # For production certificates
    bigsudo yourlabs.traefik @example.com --become -v acme=prod domain=example.com email=your@email

Note that the dashboard will be served in https://traefik.<yourdomain>,
protected by http basic auth with user "root" and password: shown by bigsudo at
the end of role, and also available in /root/password_root
