docker run -i --privileged -v $(pwd):/drone/src plugins/drone-docker <<EOF
{
    "workspace": {
        "path": "/drone/src"
    },
    "build" : {
        "number": 1,
        "head_commit": {
            "sha": "9f2849d5",
            "branch": "master",
            "ref": "refs/heads/master"
        }
    },
    "vargs": {
        "registry": REGISTRY,
        "username": USERNAME,
        "password": PW,
        "email": EMAIL,
        "repo": "angular_app",
        "storage_driver": "aufs",
        "insecure": true
    }
}
EOF